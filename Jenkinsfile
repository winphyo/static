pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Upload to AWS"'
		
            withAWS(region:'us-east-1',credentials:'aws-static') 
                {
                s3Upload(bucket: 's3jenkin-winphyo', file:'index.html');
                }
                sh '''
			echo "Upload to AWS Completed"
			ls -lah
		'''
            }
        }
    }
}

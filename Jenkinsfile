pipeline {
    agent any
    stages {
        stage('Build'){
            steps{
                sh 'echo "Hello world"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
    stage('Upload to AWS') {
        steps {
            withAWS(region:'us-west-2',credentials:'6fb5fca4-023f-4878-9844-4e26e7098e4d') {
                sh 'echo "Uploading the webapp to S3 bucket using the AWS credentials"'
                s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'src/index.html', bucket:'static-app-jenkins')
            }
        }
    }
}
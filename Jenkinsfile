pipeline {
    agent any
    stages {

        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }

        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'

                withAWS(region:'eu-west-1', credentials: 'aws-static') {
                    s3Upload(file:'index.html', bucket:'jenkinspipline-static-website-kirillos', path:'index.html')
                }

                sh 'echo "uploaded"'
            }
        }
    }
}

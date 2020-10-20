pipeline{
    agent any
    stages{
        stage('Lint HTML'){
            steps{
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS'){
            steps{
                sh 'echo "Hello World!"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                withAWS(credentials: "aws-static", region:'us-east-1') {
                    s3Upload(file:'index.html', bucket:'des1jenkins', path:'/Users/macuser/Documents/src/jenkins1/nd9991-c3-Build-CI-CD-Pipelines-Monitoring-and-Logging-v1/jenkinsfile')
                }
            }
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Navigate and Pull') {
            steps {
                dir('/home/ec2-user/jerin/wpoms-web-starter') {
                    sh 'git pull origin web_dev'
                    sh 'docker stop wpoms-web-jerin-starter || true'
                    sh 'docker rm wpoms-web-jerin-starter || true'
                    sh 'docker build -t wpoms-web-jerin-starter .'
                    sh 'docker run -d --name wpoms-web-jerin-starter --restart always -p 7778:3003 wpoms-web-jerin-starter'
                }
            }
        }
    }
}

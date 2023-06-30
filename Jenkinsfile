pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/sakshijjj/cicd.git'
                sh 'ls -ltrh '
            }
        }    
        stage('Building image ') {
            steps {
               sh ' mvn clean package install '
               sh ' docker build -t sakshijoshi522/test-cicd:$BUILD_ID . '  
            }
        }
        stage('pusing to dockerhub ') {
            steps {
               sh 'docker push sakshijoshi522/test-cicd:$BUILD_ID '
            }
        }
     }
}    

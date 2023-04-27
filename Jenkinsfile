pipeline {
    agent any
    stages {
        stage('Pulling code ') {
            steps {
               sh 'rm -rf *'
               git 'https://github.com/sakshijjj/cicd'
            }
        }
        stage('Building image ') {
            steps {
               sh 'cd cicd'
               sh 'mvn clean package install > /dev/null'
               sh 'sudo docker build -t sakshijoshi522/test-cicd:$BUILD_ID'  
            }
        }
        stage('Pushing') {
            steps {
           sh 'sudo docker push sakshijoshi522/test-cicd:$BUILD_ID'   
            }
        }
    }
}

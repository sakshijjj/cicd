pipeline {
    agent any

    stages {
        stage('Pulling code ') {
            steps {
                '''  
               rm -rf *
               git clone https://github.com/sakshijjj/cicd

                '''
            }
        }
        stage('Building image ') {
            steps {
                '''
                cd cicd
                mvn clean package install > /dev/null
                sudo docker build -t sakshijoshi522/test-cicd:$BUILD_ID .

                '''

            }
        }
        stage('Pushing') {
            steps {
                '''
              sudo docker push sakshijoshi522/test-cicd:$BUILD_ID
                '''
            }
        }
    }
}

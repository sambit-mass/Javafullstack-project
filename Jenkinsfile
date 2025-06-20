pipeline {
    agent any
    stages {
        stage ('clone') {
            steps {
                git 'https://github.com/sambit-8490/Java-Full-Stack-App.git'
            }
        }
        stage ('remove container'){
            steps {
                sh '''
                   echo y | docker system prune -a
                   '''
            }
        }
        stage ('deploy') {
            steps {
                sh '''
                   docker-compose up -d
                   '''
            }
        }
        stage ('final result') {
            steps {
                sh "echo succcessfully deploy javafullstack application"
            }
        }
    }
    post{
        always{
            mail to: 'sambitkumar.choudhuri@massoftind.com',
            subject: "Deploy java application using jenkins #${BUILD_ID}",
            body: "This is jenkins url ${BUILD_URL}"
        }
    }
        
        
}

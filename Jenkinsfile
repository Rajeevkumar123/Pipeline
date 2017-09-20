pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'make check'
            }
        }
    }
    post {
        always {
            junit '**/target/*.xml'
        }
        failure {
            mail to: naveend72599@gmail.com, subject: 'The Pipeline failed :('
        }
    }
}

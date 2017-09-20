pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'make' 
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                sh 'make check || true' 
                junit '**/target/*.xml' 
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                when {
              expression {
                currentBuild.result == null || currentBuild.result == 'SUCCESS' 
              }
            }
            steps {
                sh 'make publish'
            }
                echo 'Deploying....'
            }
        }
    }
}

  post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }

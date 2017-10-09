pipeline('python:2.7-slim') {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
               // sh 'make' 
               // archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true 
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
               // sh 'make check || true' 
                //junit '**/target/*.xml' 
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
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

pipeline {
    agent { label 'ubuntu2o' }

    stages {
        stage('Build') {
            steps {
                sh 'make --version' 
                archiveArtifacts artifacts: '*.log', fingerprint: true 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                junit '**/target/*.xml'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

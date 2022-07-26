pipeline {
    agent { label 'ubuntu2o' }

    stages {
        stage('Build') {
            steps {
                sh 'make' 
                archiveArtifacts artifacts: '*.jar', fingerprint: true 
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                junit '*.xml'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

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
                sh 'test -e ./unitt.xml && echo file exists || echo file not found'
            }
        }
        stage('Deploy') {
            when {
              expression {
                currentBuild.result == null || currentBuild.result == 'SUCCESS' 
              }
            }
            steps {
                sh 'make publish'
            }
        }
    }
}

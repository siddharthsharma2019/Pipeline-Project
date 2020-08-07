 pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                echo " This is from  Build pipeline" 
                sh 'java -version'
            }
        }
        stage('Test') { 
            steps {
                echo " This is from  test pipeline" 
                sh 'mvn -version'
            }
        }
        stage('Deploy') { 
            steps {
                echo " This is from  deploy pipeline" 
            }
        }
    }
}
 pipeline {
    agent any 
    stages {
        stage('Pull') { 
            steps {
                echo " This is from  Build pipeline" 
                git 'https://github.com/siddharthsharma2019/Pipeline-Project.git'
				sh 'java -version'				
            }
        }
        stage('Clean Build') { 
            steps {
                echo " This is from  test pipeline" 
                sh 'mvn clean package'
				sh 'mvn -version'
            }
        }
        stage('Deploy') { 
            steps {
                echo " This is from  deploy pipeline" 
				sh 'docker build -t webapp-sid .'
				sh 'docker run -itd -p 8095:8080 --name sid-webcontainer webapp-sid'
            }
        }
    }
}

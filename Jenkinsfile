 pipeline {
    agent any 
    stages 
	{
        /*stage('Pull') { 
            steps {
                echo " This is from Pull pipeline" 
                // git 'https://github.com/siddharthsharma2019/Pipeline-Project.git'
				sh 'java -version'					
            }
        }*/
        stage('Sonar Quality test') { 
            steps {
                echo " This is from Sonar test " 
                sh '/usr/share/maven sonar:sonar'				
				echo " Code is having good quality  "				
            }
        }
		stage('Clean Build') { 
            steps {
                echo " This is from  Build pipeline" 
                sh 'java -version'				
				sh 'mvn clean package'
				sh 'mvn -version'
            }
        }
        stage('Deploy') { 
            steps {
                echo " This is from deploy pipeline" 
				sh 'docker build -t webapp-sid .'
				sh 'docker stop sid-webcontainer'
				sh 'docker rm sid-webcontainer'
				sh 'docker run -itd -p 8095:8080 --name sid-webcontainer webapp-sid'
            }
        }
    }
}

pipeline {
    agent { label 'Jenkins-agent' }
    tools {
        jdk 'java17'
        maven 'maven3'
    }
    environment {
	   
    
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }

        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'github', url: 'https://github.com/deekshi17a/register-app.git'
                }
        }

        stage("Build Application"){
            steps {
                sh "mvn clean package"
            }

        }

        stage("Test Application"){
           steps {
                 sh "mvn test"
           }
       }

    }
    }
      

      
}


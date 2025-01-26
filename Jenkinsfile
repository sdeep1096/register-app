pipeline{
    agent { label 'jenkins-agent'}

    tools{
        jdk 'java 17'
        maven 'maven3'
    }
    stages{
        stage("Cleanup Workspace"){
            steps{
                cleanWs()
            }
        }
        
        stage("Checkout from SCM"){
            steps{
                git branch: 'main' , credentialsId: 'git-credentials' , url: 'https://github.com/sdeep1096/register-app'
            }
        }

        stage("Build Application"){
            steps{
                sh 'mvn clean package'
            }
        }

        stage("Test Application"){
            steps{
                sh 'mvn test'
            }
        }
        
    }
}

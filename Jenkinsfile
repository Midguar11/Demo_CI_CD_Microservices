pipeline {
    agent any
    stages{
        stage('Git Clone'){
            agent any
            steps{
                git branch: 'master', url: 'https://github.com/Midguar11/pr01_microservice-app-example.git'
            }
        }
        
       stage('Docker Run'){
            agent any       
            steps{
                sh 'sudo docker-compose up -d'
                sh 'sudo docker compose ps'
            }
        }
        
        stage("Finished Build Send email to Admin"){
            agent any       
            steps{
                emailext attachLog: true, body: 'DemoApp3 Microservices Build Completed', subject: 'DemoApp3_Microservices_pipeline', to: 'szendiattila11@gmail.com'
            }
        }
        
        stage("The countdown has started. The Demo Webshop will be deleted after 15 minutes"){
            agent any       
            steps{
                echo 'http://demoapp3.devopsempire.com/'
                echo 'http://demoapp4.devopsempire.com/'
            }
        }
    }
}
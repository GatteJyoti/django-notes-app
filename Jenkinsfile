@Library("Shared") _ 
pipeline {
    agent { label 'vinod' } 
    
    stages {
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage('Clone Code') {
            steps {
                script{
                    clone('https://github.com/GatteJyoti/django-notes-app.git','main')
                }
                 
            }
        }
        stage('Build') {
            steps {
                script{
                    code_build('notes-app','latest')
                } 
            }
        }
        stage('Push to DockerHub') {
            steps {
                script{
                    code_push('notes-app','latest','jyotigatte')
                } 
            }
        }
        stage('Deploy') {
            steps {
                 script{
                    code_deploy()
                } 
            }
        }
        
    }
}

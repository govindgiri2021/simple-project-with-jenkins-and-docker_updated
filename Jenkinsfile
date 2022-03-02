pipeline { 

    environment { 

        registry = "govindgiri2021/docker-compose-push-demo" 

        registryCredential = 'dockerhub' 

        dockerImage = '' 

    }

    agent any 

    stages { 

    
        stage('Building our image') { 

            steps { 
                sh 'sudo docker-compose build'

            } 

        }

    }

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

                script { 

                    dockerImage = sh 'sudo docker-compose build' registry + ":$BUILD_NUMBER" 

               }

            } 

        }

        stage('Deploy our image') { 

            steps { 
                 sh 'docker login -u govindgiri2021 -p Govinda@01011993'
                 sh 'docker-compose push

           }

        } 

        stage('Cleaning up') { 

            steps { 

                sh "docker rmi $registry:$BUILD_NUMBER" 

            }

        } 

    }

}



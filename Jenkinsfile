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

                script { 

                    docker.withRegistry( '', registryCredential ) { 

                        dockerImage.push() 

                    }

                } 

           }

        } 

        stage('Cleaning up') { 

            steps { 

                sh "docker rmi $registry:$BUILD_NUMBER" 

            }

        } 

    }

}



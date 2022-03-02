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

        stage('Deploy our image') { 

            steps { 
                 sh 'docker login -u govindgiri2021 -p Govinda@01011993'
                 sh 'docker-compose push govindgiri2021/docker-compose-push-demo:v1'

           }

        } 

        stage('Cleaning up') { 

            steps { 

                sh "docker rmi $registry:$BUILD_NUMBER" 

            }

        } 

    }

}



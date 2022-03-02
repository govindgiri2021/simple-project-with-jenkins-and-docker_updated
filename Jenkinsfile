pipeline {
    environment { 
        registry = "govindgiri2021/docker-compose-push-demo" 
        registryCredential = 'dockerhub' 
    }
    agent any
    
     stages {
            stage('Staging') {
            steps {
                sh 'sudo docker-compose build'
               
              }
            }
          }
          stage('Publish image to Docker Hub') {
          
            steps {
           withDockerRegistry([ credentialsId: "dockerHub", url: "govindgiri2021/docker-compose-push-demo" ]) {
          sh  'docker push govindgiri2021/docker-compose-push-demo:latest'
       
        }
                  
          }
        }
              
      }
    }
  }
}
}

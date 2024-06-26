pipeline {
 agent {label "java-build-node"}
  environment {
       DOCKERHUB_CREDENTIALS = credentials ('urvimeshram_dockerhub')    
  }
   stages{
     stage('checkout'){
       steps{
         git: "https://github.com/urwashi-lav/docker-project.git" branch: "main" 
       }
     }
     stage ('build docker image'){
       steps{
         sh 'docker build -t urvimeshram/doc:$BUILD_NUMBER. '
       }
     }
    stage ('login to dockerhub'){
     steps{
      sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u="$DOCKER_USERNAME" -p="$DOCKER_PASSWORD"'
     }
    }
    stage ('push image'){
     steps{
      sh 'docker push urvimeshram/doc:$BUILD_NUMBER' 
     }
    }
   }
 post{
  always{
   sh 'docker logout'
  }
 }
 
}

pipeline {
 agent {labels "java-build-node"}
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
      sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login  -u DOCKERHUB_CREDENTIALS_USR --password-stdin'
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

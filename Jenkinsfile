pipeline {
  agent any

  environment{
    docker image = ''
    registry = 'urvimeshram/docker'
  }

  stages {
    stage ('checkout'){
      steps{
        checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/urwashi-lav/docker-project.git']])
      }
    }

    stage ('build docker image'){
       steps{
         script{
           docker image = docker.build registry
         }
       }      
    }


    
  }

}

pipeline {
  agent any

  environment{
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
  }

  stages {
    stage ('checkout'){
      steps{
        checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/urwashi-lav/docker-project.git']])
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

pipeline {
 agent any
  environment {
    
  }
   stages{
     stage{
       steps('checkout'){
         git: "https://github.com/urwashi-lav/docker-project.git" branch: "main" 
       }
     }
     stage{
       steps('enter the ec2'){
         sh 'ssh -i "docker-key.pem" ec2-user@ec2-13-201-117-152.ap-south-1.compute.amazonaws.com'
         sh 'apt-get update -y'
       }
     }
     

   
   
   
   
   }
}

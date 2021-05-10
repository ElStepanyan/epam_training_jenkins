pipeline {
    agent { label 'master' }
    
 stages{
    stage ('Build') {
        steps{

           sh 'mvn -B -DskipTests clean package'
        }
        
    }
    stage("create docker image"){
          steps{ 
            sh 'docker build -t nexus.local:8082/demo .'
          
          }
      }    
     stage("push image to nexus"){
         steps{
         sh 'docker push nexus.local:8082/demo'
         }
     }
   }   
}

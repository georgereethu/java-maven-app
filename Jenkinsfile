pipeline{
 agent any
 tools{
 maven 'maven-3.9'
 }
 stages{
  stage("build"){
  steps{
      sh 'mvn package'
     }
  }
   stage("Test"){
  

        steps{
          echo  "Test is successful"
               }
   
}

     stage("Build Image"){
  
       steps{
        withCredentials([usernamePassword(credentials: 'dockerhub_cred', usernameVariable: 'USER', passwordVariable: 'USER')]){
         sh 'docker build -t reethu123/myrepo:1.2 . '
         sh "echo $PASS |docker login -u $USER --password-stdin"
         sh 'docker push reethu123/myrepo:1.2'
        }
       }
     

}

      stage("Deploying Image"){

        steps{
         echo "Deploying docker image to Docker hub"
      }
      }

      

     }

   }


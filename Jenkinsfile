def gv
pipeline{
 agent any
 tools{
 maven 'maven-3.9'
 }
 stages{
  stage("initilization stage"){
   steps{
    script{
     gv = load ("script.groovy")
    }
   }
  }
  stage("build"){
  steps{
   script{
      gv.buildJar()
     }
   }
  }
   stage("Test"){
        steps{
         script {
          gv.testApp()
               }
        }
}

     stage("Build Image"){
  
       steps{
        withCredentials([usernamePassword(credentialsId: 'docker_hub_cred', usernameVariable: 'USER', passwordVariable: 'PASS')]){
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

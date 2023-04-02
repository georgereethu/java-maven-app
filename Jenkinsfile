#!/usr/bin/env groovy
@Library('jenkins-shared-library')_

pipeline{
 agent any
 tools{
 maven 'maven-3.9'
 }
 stages{
  stage("build"){
  steps{
      buildJar()
     }
  }
   stage("Test"){
        steps{
          echo  "Test is successful"
               }
}

     stage("Build Image"){
  
       steps{
        buildImage()
        }
       }
  
      stage("Deploying Image"){

        steps{
         echo "Deploying docker image to Docker hub"
      }
      }    
     }
   }


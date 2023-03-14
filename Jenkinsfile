pipeline{
 agent any
 parameters{
  choice(name: 'VERION', choices: ['1.1.0', '1.2.0', '1.3.0'], description:'')
  booleanParam(name: 'executeTests', defaultValue: true, description:'')

 }
 stages{
  stage("build"){
   steps{
    echo  "Build is successful"
   }
  }
   stage("Test"){
   when{
   expression {
   params.executeTests==true
   }
   }
     steps{
      echo  "Test is successful"
     }
    }

     stage("Deploy"){
       steps{
        echo  "Deploy is successful"
        echo "Deploying ${params.VERSION}"
       }
     }
 }
}

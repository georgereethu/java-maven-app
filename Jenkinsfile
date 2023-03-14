pipeline{
 agent any
 parameters{
  choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description:'')
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
      input {
       message "Select the environment to deploy to:"
       ok "ENV selected"
       parameters {
        choice(name: 'ENV', choices: ['Dev', 'Staging', 'Prod'], description:'')
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description:'')
       }
      }
       steps{
        echo  "Deploy is successful"
        echo "Deploying to  ${ENV}"
        echo "Deploying to  ${VERSION}"
       }
     }
 }
}

pipeline{

    environment{

        CURR_VERSION = 1.0.0

    }

  agent any
  
  stages{
  
    stage("build"){
      steps{
      echo "hello world"
      echo "Product version = ${CURR_VERSION}"
      }
    }
    
    stage("test"){
      steps{
      echo "in the test"
      }
    
    }
    stage("deploy"){
      steps{
      echo "in the deploy"
      }
    }
  }


}

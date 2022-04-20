pipeline{
  agent any

  parameters{
      choice(name:"VERSION",choices:['1.0.0','1.0.1' , '1.1.1','2.0.0'],description:'')
      booleanParam(name:'executeTest',defaultValue:true,description:'')

  }
  
  stages{
  
    stage("build"){
      steps{
      echo "hello world"
    
      }
    }
    
    stage("test"){
        when{
            expression{
                params.executeTest
            }
        }
      steps{
      echo "in the test"
      }
    
    }
    stage("deploy"){
      steps{
      echo "in the deploy"
      echo "Current deployment version : ${params.VERSION}"
      }
    }
    stage("schedule cron"){
        steps{
        script{
            println("Scheduling my cron after 2 min")
            def exp = cron("*/2 * * * *")
            def trigger = []
            trigger >> exp 
            properties([pipelineTriggers(trigger)])
        }
        }
    }
  }


}

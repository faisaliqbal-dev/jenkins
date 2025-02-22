pipeline{
    agent any
    parameters {
        string (name: "faisal" , defaultValue: "faisal" , description: "who are you?")
        booleanParam (name: "ismale" , defaultValue: true , description: "who are you?")
        choice (name: 'city' , choices: ['nanded' , 'nagpur' , 'mumbai' , 'pune'] , description: "select your city")
    }
    environment {
        name = 'faisal'
    }
    stages{
        stage("build"){
            steps{
                echo "this is building stage"
            }           
        }
        stage("test"){
            steps{
                echo "this is testing stage"
            }
        }
        stage("variable"){
            steps{
                echo "my name is ${name}"
            }
        }
        stage("continue?"){
             input {
                 message "should we cotinue"
                 ok "yes"
            steps{
                echo " deploying on prod stage"
            }
        }
        stage("deploy-on-prod"){
            steps{
                echo "this is deploying on prod stage"
            }
        }
         stage("shell-script"){
            steps{
                sh '''pwd
                        ls
                      date
                   ls -la'''
            }
        }
  }
     post{
        always{
            echo "this is message will always print"
        }
        success{
            echo "pipeline executed successfully "
        }
        failure{
            echo "pipeline execution failed"
        }
     }
}

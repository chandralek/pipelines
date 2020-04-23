pipeline {
    agent any

  environment{
    COURSE_NAME = "Devops"
  }

  parameters {
    string(name: 'TIMING', defaultValue: '', description: 'TIMING')
    booleanParam(name: 'YES', defaultValue: '', description: 'Run 2?')
  }

    stages {
        stage('One') {
            steps{
                script{
                    print " Course = " +COURSE_NAME
                    print " Time = " +TIMING
                }
            }
        }

      stage('Two') {
        when {
          // Only say hello if a "greeting" is requested
          expression { return  params.YES}
        }
        steps{
          sh 'echo Hello from stage 2'
        }
      }

      stage('multistage') {
        parallel{
          stage(mutlistage1){
            steps{
              sh 'echo Hello from stage 2'
            }
          }
          stage(mutlistage2){
            steps{
              sh 'echo Hello from stage 2'
            }
          }
        }

      }
    }

}

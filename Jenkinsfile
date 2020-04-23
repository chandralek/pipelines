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
          sh 'Hello from stage 2'
        }
      }

    }

}

pipeline {
    agent any

  environment{
    COURSE_NAME = "Devops"
  }

  parameters { string(name: 'TIMING', defaultValue: '', description: 'TIMING') }
    stages {
        stage('One') {
            steps{
                script{
                    print " Course = " +COURSE_NAME
                    print " Time = " +TIMING
                }
            }
        }

    }

}

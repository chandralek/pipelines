pipeline {
  agent any

  stages {

    stage('Dynamically generate branches') {
      steps {
        dir('app') {
          git url: "https://github.com/chandralek/learning.git", credentialsId: "GitUserPass"
          sh '''
          git branch -r  | awk -F '/' '{print $2}' |sed -n '2,$ p' > branch.txt
          '''
        }
      }
    }
    stage('Parameter'){
      steps{
        script{
          list = readFile "${env.WORKSPACE}/app/branch.txt"
          parameters {
            choiceParam('BRANCH_NAME',"${list}",'Pick something')
          }
        }
      }
    }
  }
}
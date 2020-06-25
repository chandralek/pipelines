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
    stage(''){
      steps{
        script{
          readFile "${env.WORKSPACE}/app/branch.txt"
          parameters: [choice(name: 'BRANCH_NAME', choices: "${liste}", description: 'Branch to build?')]
        }
      }
    }
  }
}
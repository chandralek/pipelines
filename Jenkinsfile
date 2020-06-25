pipeline {
  agent any

  stages {

    stage('Dynamically generate branches') {
      steps {
        dir('app') {
          git url:"https://github.com/chandralek/learning.git" ,credentialsId: "GitUserPass"
          sh '''
          git branch -r  | awk -F '/' '{print $2}' |sed -n '2,$ p' > branches.txt
          '''
          liste = readFile 'branches.txt'
          parameters: [choice(name: 'BRANCH_NAME', choices: ${liste}, description: 'Branch to build?')]
          git branch: ${BRANCH_SCOPE},
          credentialsId: 'GitUserPass',
          url: 'https://github.com/chandralek/learning.git'

          sh '''ls -lat'''
        }
      }
    }
  }
}
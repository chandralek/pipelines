pipeline {
  agent any

  parameters {
    string(name: 'BRANCH',defaultValue: '',description: 'BRANCH')
  }

  stages {

    stage('Clone Branch') {
      steps {
        dir('app') {
          checkout([$class: 'GitSCM', branches: [[name: '*/${BRANCH}']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GitUserPass', url: 'https://github.com/chandralek/learning.git']]])
        }
      }
    }
  }
}
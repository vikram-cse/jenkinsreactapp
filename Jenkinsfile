pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''npm install
'''
        echo 'NPM packages has been loaded...'
      }
    }
  }
  environment {
    CI = 'true'
    Home = '.'
    PORT_NUMBER = '9090'
  }
}
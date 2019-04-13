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
    stage('Test') {
      steps {
        sh 'bash ./jenkins/script/test.sh'
        input(message: 'Wait for test to success and ready to complete', ok: 'Yes and continue to build?')
      }
    }
  }
  environment {
    CI = 'true'
    Home = '.'
    PORT_NUMBER = '9090'
  }
}
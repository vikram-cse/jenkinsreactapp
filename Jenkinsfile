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
        sh 'bash ./jenkins/scripts/test.sh'
        input(message: 'Wait for test to success and ready to complete', ok: 'Yes and continue to build?')
      }
    }
    stage('Deliver and Stop') {
      steps {
        sh 'bash ./jenkins/scripts/deliver.sh'
        input(message: 'Have you tested React application', ok: 'Yes, I haveready to stop server')
        sh 'bash ./jenkins/scripts/kill.sh'
      }
    }
  }
  environment {
    CI = 'true'
    Home = '.'
    PORT_NUMBER = '9090'
  }
}
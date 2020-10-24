pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'This is build Stage'
      }
    }

    stage('Test') {
      steps {
        echo 'This is Test step'
      }
    }

    stage('deployment') {
      steps {
        input(message: 'Please approve deployment', id: '1', ok: 'yes')
      }
    }

  }
}
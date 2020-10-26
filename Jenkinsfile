pipeline {
  agent any
  stages {
    stage('vtest') {
      steps {
        sh '''#!/bin/bash
echo My Full-name is $fname $lname'''
      }
    }

  }
  environment {
    fname = 'kashif'
    lname = 'mehmood'
  }
}
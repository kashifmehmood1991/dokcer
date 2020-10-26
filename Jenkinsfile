pipeline {
  agent any
  stages {
    stage('uncompress the source') {
      steps {
        sh '''#/bin/bash
unzip helloworld-master.zip
cd helloworld-master'''
      }
    }

    stage('build step') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('build artifacts') {
      steps {
        archiveArtifacts(allowEmptyArchive: true, artifacts: 'target/helloworld-1.0.jar', fingerprint: true)
      }
    }

    stage('Deployment') {
      steps {
        input(message: 'Do you want to proceed for deployment', id: 'deployment', ok: 'yes')
      }
    }

  }
}
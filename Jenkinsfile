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
        sh '''cd helloworld-master
mvn clean package'''
      }
    }

    stage('build artifacts') {
      steps {
        archiveArtifacts(allowEmptyArchive: true, artifacts: 'helloworld-master/target/helloworld-1.1.jar', fingerprint: true)
      }
    }

    stage('Deployment') {
      agent any
      steps {
        input(message: 'Do you want to proceed for deployment', id: 'deployment', ok: 'yes')
        echo 'Deployment is successfull'
      }
    }

  }
}
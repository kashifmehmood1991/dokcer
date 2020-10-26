pipeline {
  agent any
  stages {
    stage('build the artficats') {
      steps {
        archiveArtifacts(allowEmptyArchive: true, fingerprint: true, artifacts: '*.txt')
      }
    }

  }
}
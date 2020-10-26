pipeline {
  agent none
  stages {
    stage('Build') {
      parallel {
        stage('BuildA') {
          steps {
            echo 'This is jdk8 build'
          }
        }

        stage('BuildB') {
          steps {
            echo 'This is jdk 7 build'
          }
        }

      }
    }

    stage('Test') {
      parallel {
        stage('TestA') {
          steps {
            echo 'This is Test A'
          }
        }

        stage('TestB') {
          steps {
            echo 'This is test B'
          }
        }

      }
    }

    stage('Deployment') {
      parallel {
        stage('Deployment') {
          steps {
            echo 'Deployment on Windows'
          }
        }

        stage('linux') {
          steps {
            echo 'Deployment on linux'
          }
        }

      }
    }

  }
}
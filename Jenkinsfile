pipeline {
  agent none
  stages {
    stage('Build') {
      parallel {
        stage('BuildA') {
          agent {
            node {
              label 'jdk8node'
            }

          }
          steps {
            echo 'This is jdk8 build'
          }
        }

        stage('BuildB') {
          agent {
            node {
              label 'jdk7node'
            }

          }
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
          agent {
            node {
              label 'windowsA'
            }

          }
          steps {
            echo 'Deployment on Windows'
          }
        }

        stage('linux') {
          agent {
            node {
              label 'linuxnode'
            }

          }
          steps {
            echo 'Deployment on linux'
          }
        }

      }
    }

  }
}
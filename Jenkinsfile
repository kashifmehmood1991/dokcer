pipeline {
  agent none
  stages {
    stage('Build') {
      parallel {
        stage('BuildA') {
          when {
            not {
              branch 'multibranchtesting'
            }

          }
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
            emailext(subject: 'Deployment on production', body: 'Your approval is required to deploy on production', from: 'kashifmehmood_1991@yahoo.com', to: 'kashifmehmood_1991@yahoo.com', replyTo: 'kashifmehmood_1991@yahoo.com')
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
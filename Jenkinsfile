pipeline {
  agent {
    docker {
      image 'nginx:latest'
    }

  }
  stages {
    stage('Test Stage') {
      environment {
        envTest = 'yo this is from berrabe'
      }
      parallel {
        stage('whoami') {
          steps {
            dockerNode(image: 'ubuntu') {
              sh 'hostname && cat /etc/passwd /etc/*release'
            }

          }
        }

        stage('Shell') {
          steps {
            sh 'hostname && pwd && ls -lhtr'
          }
        }

        stage('Print Stage Environment') {
          steps {
            sh 'hostname && echo $envTest'
          }
        }

      }
    }

  }
}
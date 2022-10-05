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
            sh 'cat /etc/passwd'
          }
        }

        stage('Shell') {
          steps {
            sh 'hostname && pwd && ls -lhtr'
          }
        }

        stage('Print Stage Environment') {
          steps {
            sh 'echo $envTest'
          }
        }

      }
    }

  }
}
pipeline {
  agent any
  stages {
    stage('Test Stage') {
      environment {
        envTest = 'yo this is from berrabe'
      }
      parallel {
        stage('whoami') {
          steps {
            sh 'whoami'
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
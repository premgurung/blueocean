pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
      }
    }

    stage('Testing') {
      parallel {
        stage('Testing') {
          steps {
            echo 'Testing '
          }
        }

        stage('Integration Test') {
          steps {
            echo 'Testing '
          }
        }

        stage('Performance Testing') {
          steps {
            timeout(time: 90) {
              echo 'performance testing'
            }

          }
        }

      }
    }

    stage('PrePod') {
      steps {
        echo 'PreProd  Env'
      }
    }

    stage('Prod') {
      when {
        branch 'master'
      }
      steps {
        echo 'Production'
      }
    }

  }
}
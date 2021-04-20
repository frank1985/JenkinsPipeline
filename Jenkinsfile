pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the application'
          }
        }

        stage('Deploy') {
          steps {
            echo 'Deploying app in iSS server'
          }
        }

      }
    }

  }
}
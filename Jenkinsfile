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
            echo "Get ${ChromeDriverPath}"
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
  environment {
    ChromeDriverPath = 'C:\\Drivers\\Chrome'
  }
}
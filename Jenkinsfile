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

        stage('Test Log') {
          steps {
            writeFile(file: 'LogTestFile.txt', text: 'This is an automated log file')
            writeFile(file: 'LogTestFile.txt', text: 'This is an automated log file')
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to deploy?', id: 'OK')
        echo 'Deploying app in iSS server'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\Drivers\\Chrome'
  }
}
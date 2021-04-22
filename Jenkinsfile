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
          environment{
            LocalVariable = "HelloLocal"
          }
          steps {
            writeFile(file: 'LogTestFile.txt', text: "This is the chromedriver path ${ChromeDriverPath} and this is the value of the local variable ${LocalVariable}")
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to deploy?', id: 'OK')
            echo 'Deploying app in iSS server'
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    localVar
    ChromeDriverPath = 'C:\\Drivers\\Chrome'
  }
}
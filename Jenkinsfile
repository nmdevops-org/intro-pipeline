pipeline {
  agent {
    label 'jdk9'
  }
  stages {
    stage('Say Hello') {
      parallel {
        stage('Say Hello') {
          steps {
            echo "Hello ${MY_NAME}!"
          }
        }
        stage('Dump Java Version') {
          steps {
            sh 'java -version'
          }
        }
      }
    }
  }
  environment {
    MY_NAME = 'Mary'
  }
}
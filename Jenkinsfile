pipeline {
  agent any
  stages {
    stage('Say Hello') {
      parallel {
        stage('Say Hello') {
          steps {
            echo 'Hello World'
          }
        }
        stage('') {
          steps {
            sh 'java -version'
          }
        }
      }
    }
  }
}
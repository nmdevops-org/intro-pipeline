pipeline {
  agent {
    label 'jdk9'
  }
  stages {
    stage('Say Hello') {
      parallel {
        stage('Say Hello') {
          steps {
            echo 'Hello World'
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
}
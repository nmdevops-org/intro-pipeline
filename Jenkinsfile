pipeline {
  agent {
    label 'jdk9'
  }
  stages {
    stage('Deploy') {
      options {
        timeout(time: 30, unit: 'SECONDS')
      }
      input {
        message 'Should we continue?'
      }
      steps {
        echo 'Continuing with deployment'
      }
    }
    stage('Say Hello') {
      parallel {
        stage('Say Hello') {
          steps {
            echo "Hello ${params.Name}!"
            echo "Hello ${MY_NAME}!"
            echo "${TEST_USER_USR}"
            echo "${TEST_USER_PSW}"
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
    TEST_USER = credentials('test-user')
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}
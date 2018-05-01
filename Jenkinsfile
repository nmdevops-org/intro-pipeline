pipeline {
  agent {
    label 'jdk8'
  }
  stages {
    stage('Deploy') {
      options {
        timeout(time: 30, unit: 'SECONDS')
      }
      input {
        message 'Which Version?'
        id 'Deploy'
        parameters {
          choice(name: 'APP_VERSION', choices: 'v1.1 v1.2 v1.3', description: 'What to deploy?')
        }
      }
      steps {
        echo "Deploying ${APP_VERSION}."
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
            sh 'java -version'
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
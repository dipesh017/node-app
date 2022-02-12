pipeline {
  agent any
  stages {
    stage('Unit Testing') {
      parallel {
        stage('Unit Testing') {
          steps {
            sh 'npm test'
          }
        }

        stage('Sample Stage') {
          steps {
            sh 'ls'
          }
        }

      }
    }

    stage('Build ') {
      steps {
        sh 'npm build'
      }
    }

    stage('Docker Build') {
      steps {
        sh '''docker build -t demo/demo:v1
docker push demo/demo:v1'''
      }
    }

  }
  environment {
    APP_NAME = 'sample-app'
    Key = 'value'
  }
}
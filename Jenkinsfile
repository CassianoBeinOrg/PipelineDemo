pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build Frontend') {
          agent any
          steps {
            echo 'Build with JDK8'
            sh 'java -version'
          }
        }
        stage('Build Backend') {
          agent {
            label 'nodejs-app'
          }
          steps {
            echo 'Build done'
          }
        }
      }
    }
    stage('Test UI') {
      parallel {
        stage('Test UI') {
          agent any
          steps {
            echo 'test done'
            sleep 15
          }
        }
        stage('Test Backend APIs') {
          agent any
          steps {
            echo 'test done'
            sleep 15
          }
        }
        stage('Test 3rd party APIs') {
          agent any
          steps {
            echo 'test done'
            sleep 15
          }
        }
        stage('Test Dependencies') {
          agent any
          steps {
            echo 'test done'
            sleep 15
          }
        }
      }
    }
    stage('Deploy to Performance Env') {
      parallel {
        stage('Deploy to Performance Env') {
          agent any
          steps {
            echo 'deploy done'
          }
        }
        stage('Performance test') {
          agent any
          steps {
            sleep 30
          }
        }
      }
    }
    stage('Approval gate') {
      steps {
        input(message: 'Aprove Deploy to Prod?', id: 'DeployProd')
      }
    }
    stage('Deploy to Prod') {
      agent any
      steps {
        echo 'Deploy done !'
      }
    }
  }
}
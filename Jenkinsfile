pipeline {
  agent any
  stages {
    stage('Build') {
      agent {
        node {
          label 'jdk8'
        }

      }
      steps {
        echo 'Build with JDK8'
        sh 'java -version'
      }
    }
    stage('Test UI') {
      parallel {
        stage('Test UI') {
          steps {
            echo 'test done'
          }
        }
        stage('Test Backend APIs') {
          steps {
            echo 'test done'
          }
        }
        stage('Test 3rd party APIs') {
          steps {
            echo 'test done'
          }
        }
        stage('Test Dependencies') {
          steps {
            echo 'test done'
          }
        }
      }
    }
    stage('Deploy to Performance Env') {
      parallel {
        stage('Deploy to Performance Env') {
          steps {
            echo 'deploy done'
          }
        }
        stage('Performance test') {
          steps {
            sleep 15
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
      steps {
        echo 'Deploy done !'
      }
    }
  }
}
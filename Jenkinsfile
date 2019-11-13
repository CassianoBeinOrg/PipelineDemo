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
          agent any
          steps {
            echo 'test done'
          }
        }
        stage('Test Backend APIs') {
          agent any
          steps {
            echo 'test done'
          }
        }
        stage('Test 3rd party APIs') {
          agent any
          steps {
            echo 'test done'
          }
        }
        stage('Test Dependencies') {
          agent any
          steps {
            echo 'test done'
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
      agent any
      steps {
        echo 'Deploy done !'
      }
    }
  }
}
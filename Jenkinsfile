pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'build complete'
      }
    }
    stage('tests') {
      parallel {
        stage('UI tests') {
          steps {
            echo 'UI test done!'
          }
        }
        stage('Services Tests') {
          steps {
            echo 'Services Tests done'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy done'
      }
    }
  }
}
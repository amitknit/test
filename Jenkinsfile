pipeline {
  agent any
  stages {
    stage('Download from SVN') {
      steps {
        echo 'Download from SVN'
      }
    }
    stage('Sleep') {
      steps {
        sleep 30
      }
    }
    stage('Deploy application') {
      parallel {
        stage('Deploy application') {
          steps {
            sh 'echo Deploying my application'
            node(label: 'master') {
              sh 'echo I am in main directory'
              sleep 2
              echo 'after 2 sec sleep'
            }

          }
        }
        stage('Deploy another app') {
          steps {
            sh 'echo deploying app2'
          }
        }
      }
    }
    stage('Final check') {
      steps {
        echo 'Checking finally'
      }
    }
  }
  environment {
    param1 = 'amit'
    param2 = 'amit2'
  }
}
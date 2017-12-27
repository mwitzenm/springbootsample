pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        echo 'Build'
        sh 'oc start-build store-orders'
      }
    }
    stage('Test') {
      agent {
        node {
          label 'gradle'
        }
        
      }
      steps {
        sh '''grade bootrun
ls -lrt'''
      }
    }
  }
  environment {
    name = 'dev'
  }
}
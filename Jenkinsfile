pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'pull finish!'
        sh 'mvn deploy'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }
  }
}
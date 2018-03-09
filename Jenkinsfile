pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        build 'fastjson'
        echo 'pull finish!'
      }
    }
    stage('Test') {
      steps {
        timestamps()
      }
    }
  }
}
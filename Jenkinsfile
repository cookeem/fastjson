pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args  '-H tcp://docker:2375 --user root'
    }
  }
  stages {
    stage('Build') {
      steps {
        sh 'id'
        sh 'whoami'
        sh 'pwd'
        sh 'mvn --version'
        sh 'mvn clean install'
        sh 'ls -l target'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing....'
        sh 'pwd'
        sh 'which mvn'
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy finish!!'
      }
    }
  }
}

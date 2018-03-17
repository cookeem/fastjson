pipeline {
  options {
    timestamps()
    retry(3)
  }
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          docker.withTool("docker") {
            withDockerServer([uri: "tcp://docker:2375"]) {
              docker.image('maven:3.5.3').inside('--user root') {
                sh 'id'
                sh 'whoami'
                sh 'pwd'
                sh 'mvn --version'
                sh 'mvn clean install'
                sh 'ls -l target'
              }
            }
          }
        }
        
      }
    }
    stage('Test') {
      steps {
        echo 'Testing....'
        sh 'pwd'
        sh 'ls -l target'
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy finish!!'
      }
    }
  }
}

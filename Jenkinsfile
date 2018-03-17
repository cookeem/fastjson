pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          docker.withTool("docker") {
            withDockerServer([uri: "tcp://docker:2375"]) {
              docker.image('devops-reg.io/public/maven:3.5.3').inside('--user root -v /var/jenkins_home/.m2:/root/.m2') {
                sh 'id'
                sh 'whoami'
                sh 'pwd'
                sh 'ls -al ~/.m2'
                sh 'cat ~/.m2/settings.xml'
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

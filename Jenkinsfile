pipeline {
  options {
    timestamps()
    retry(3)
  }
  agent any
  stages {
    stage('Build') {
      input {
        message "Should we continue?"
        ok "Yes, we should."
        parameters {
          string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        }
      }
      steps {
        script {
          docker //.withTool("docker") {
            withDockerServer([uri: "tcp://docker:2375"]) {
              docker.image(/*'maven:3.5.3'*/ 'alpine').inside('--user root') {
                echo "Hello, ${PERSON}, nice to meet you."
                sh 'cat /etc/alpine-release'
                sh 'id'
                sh 'whoami'
                sh 'pwd'
                //sh 'mvn --version'
                //sh 'mvn clean install'
                //sh 'ls -l target'
              }
            }
          //}
        }
        
      }
    }
    stage('Test') {
      steps {
        echo 'Testing....'
        sh 'pwd'
        //sh 'ls -l target'
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy finish!!'
      }
    }
  }
}

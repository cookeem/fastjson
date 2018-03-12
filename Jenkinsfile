node {
    stage('Build') {
        docker.withTool("docker") {
            withDockerServer([uri: "tcp://docker:2375"]) {
                docker.image('node:7-alpine').inside {
                    sh 'printenv'
                    sh 'node --version'
                }
            }    
        }
    }
    stage('Test') {
        echo 'Testing....'
    }
}

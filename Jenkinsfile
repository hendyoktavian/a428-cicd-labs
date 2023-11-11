node {
    docker.image('node:10.11.0-alpine').withRun('-p 3000:3000') {
        stage('Build') {
            sh 'npm install'
        }

        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }
    }
}

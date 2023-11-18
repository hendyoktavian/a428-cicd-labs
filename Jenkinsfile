node {
    docker.image('node:16-buster-slim').withRun('-p 3000:3000') {
        stage('Build') {
            sh 'chmod 777 /var/lib/apt/lists'
            sh 'chmod 777 /var/lib/apt/lists/*'
            
            sh 'apt-get update && apt-get install -y npm'
            sh 'npm install'
        }

        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }
    }
}
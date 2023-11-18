node {
    docker.image('node:16-buster-slim').withRun('-p 3000:3000') {
        stage('Build') {
            sh 'sudo chmod 777 /var/lib/apt/lists'
            sh 'sudo chmod 777 /var/lib/apt/lists/*'
            
            sh 'sudo apt-get update && sudo apt-get install -y npm'
            sh 'npm install'
        }

        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }
    }
}
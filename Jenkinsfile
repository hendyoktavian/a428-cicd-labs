node {
    // Menentukan agent Docker
    docker.image('node:16-buster-slim').withRun('-p 3000:3000') {
        // Stage Build
        stage('Build') {
            // Memberikan izin yang diperlukan menggunakan sudo
            sh 'sudo chmod 777 /var/lib/apt/lists'
            sh 'sudo chmod 777 /var/lib/apt/lists/*'
            
            // Update dan install npm
            sh 'sudo apt-get update && sudo apt-get install -y npm'
            sh 'npm install'
        }

        // Stage Test
        stage('Test') {
            // Steps untuk Test
            sh './jenkins/scripts/test.sh'
        }
    }
}
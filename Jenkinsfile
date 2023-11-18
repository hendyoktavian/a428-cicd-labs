node {
    // Menentukan agent Docker
    docker.image('node:16-buster-slim').withRun('-p 3000:3000') {
        // Stage Build
        stage('Build') {
            // Memberikan izin yang diperlukan langsung sebagai root
            sh 'chown -R root:root /var/lib/apt/lists'
            
            // Update dan install npm
            sh 'apt-get update && apt-get install -y npm'
            sh 'npm install'
        }

        // Stage Test
        stage('Test') {
            // Steps untuk Test
            sh './jenkins/scripts/test.sh'
        }
    }
}
node {
    // Menentukan agent Docker
    docker.image('node:16-buster-slim').withRun('-p 3000:3000') {
        // Stage Build
        stage('Build') {
            // Update dan install npm tanpa mengubah kepemilikan
            sh 'apt-get update && apt-get install -y --no-install-recommends npm'
            sh 'npm install'
        }

        // Stage Test
        stage('Test') {
            // Steps untuk Test
            sh './jenkins/scripts/test.sh'
        }
    }
}
node {
    // Menentukan agent Docker
    docker.image('node:16-buster-slim').inside('-p 3000:3000') {
        // Stage Build
        stage('Build') {
            // Steps untuk Build
            sh 'npm install'
        }

        // Stage Test
        stage('Test') {
            // Steps untuk Test
            sh './jenkins/scripts/test.sh'
        }
    }
}
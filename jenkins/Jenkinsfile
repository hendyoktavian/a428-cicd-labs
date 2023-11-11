node {
    // Gunakan image Docker 'node:lts-buster-slim' dengan port mapping -p 3000:3000
    docker.image('node:lts-buster-slim').withRun('-p 3000:3000') {
        // Set environment variable CI='true'
        env.CI = 'true'

        // Stage 'Build'
        stage('Build') {
            // Langkah untuk menjalankan npm install
            sh 'npm install'
        }

        // Stage 'Test'
        stage('Test') {
            // Langkah untuk menjalankan test.sh dari direktori ./jenkins/scripts/
            sh './jenkins/scripts/test.sh'
        }

        // Stage 'Deliver'
        stage('Deliver') {
            // Langkah untuk menjalankan deliver.sh
            sh './jenkins/scripts/deliver.sh'

            // Input step untuk menunggu interaksi pengguna
            input message: 'Finished using the website? (Click "Proceed" to continue)'

            // Langkah untuk menjalankan kill.sh setelah input diterima
            sh './jenkins/scripts/kill.sh'
        }
    }
}

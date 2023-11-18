node {
    docker.image('node:16-buster-slim').inside('-p 3000:3000') {
        stage('Build') {
            sh 'npm install'
        }

        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }

        stage('Manual Approval') {
            input message: 'Lanjutkan ke tahap Deploy?', ok: 'Proceed', submitter: 'user'
        }

        stage('Deploy') {
            sh './jenkins/scripts/deliver.sh'
            sleep time: 60
            sh './jenkins/scripts/kill.sh'
        }
    }
}

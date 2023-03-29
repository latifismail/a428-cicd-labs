node {
    withDockerContainer(image: 'node:16-buster-slim', args: '-p 3000:3000') {
        stage('Build') {
            sh 'npm install'
        }
        stage('Test') {
            sh './jenkins/scripts/test.sh'
        }
        stage('Deploy') {
            sh './jenkins/scripts/deliver.sh'
            sh 'sleep 1m'
            sh './jenkins/scripts/kill.sh'
        }
    }
}
node {
    withDockerContainer('maven:3.8.7-eclipse-temurin-11') {
        stage('Build') { 
            sh 'mvn -B -DskipTests clean package' 
        }
        stage('Test') {
            sh 'mvn test'
        }
        stage('Deliver') { 
            sh './jenkins/scripts/deliver.sh' 
        }
        stage('Manual Approval') {
            input message: 'Lanjutkan ke tahap Deploy? (Klik "Proceed" untuk mengakhiri)' 
        }
        stage('Deploy') { 
            sh './jenkins/scripts/deliver.sh' 
            sleep 60
            input message: 'Sudah selesai menggunakan Simple Java App? (Klik "Proceed" untuk mengakhiri)' 
            sh './jenkins/scripts/kill.sh' 
        }
    }
}
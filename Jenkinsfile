node {
    withDockerContainer('maven:3.8.7-eclipse-temurin-11') {
        stage('Build') { 
            sh 'mvn -B -DskipTests clean package' 
        }
        stage('Test') {
            sh 'mvn test'
        }
        stage('Manual Approval') {
            input message: 'Lanjutkan ke tahap Deploy? (Klik "Proceed" untuk melanjutkan)'
        }
        stage('Deploy') { 
            sh './jenkins/scripts/deliver.sh' 
            sleep 60
            return
        }   
    }
}
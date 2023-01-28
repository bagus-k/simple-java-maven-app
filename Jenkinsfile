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
    }
}
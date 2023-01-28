

node {
    withDockerContainer('maven:3.8.7-eclipse-temurin-11') {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
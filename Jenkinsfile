pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                sh '/opt/maven/bin/mvn compile'
            }
        }

        stage('Unit Test') {
            steps {
                sh '/opt/maven/bin/mvn test'
            }
        }

        stage('Package') {
            steps {
                sh '/opt/maven/bin/mvn package'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.war', fingerprint: true
        }
    }
}

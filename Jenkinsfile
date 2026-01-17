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

        failure {
            mail to: 'your-email@gmail.com',
                 subject: "Jenkins Build Failed: ${JOB_NAME}",
                 body: """Build failed!

Job Name: ${JOB_NAME}
Build Number: ${BUILD_NUMBER}
Build URL: ${BUILD_URL}
"""
        }
    }
}


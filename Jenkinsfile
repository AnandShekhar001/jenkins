pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

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
}


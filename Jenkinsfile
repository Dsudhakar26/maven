pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                withMaven(maven : 'jenkin-Maven') {
                  sh 'mvn clean compile'
                }
            }
        }
        stage('Test') {
            steps {
                withMaven(maven : 'jenkin-Maven') {
                  sh 'mvn test'
                }
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                sh 'echo "delivered"'
            }
        }
    }
}

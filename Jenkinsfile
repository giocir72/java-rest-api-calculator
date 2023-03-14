pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/giocir72/java-rest-api-calculator.git'

                // Run Maven on a Unix agent.
                sh "./mvnw clean compile"
            }
        }
        stage('Test') {
            post {
                always {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
            steps {
                sh "mvn test"
            }
        }
    }
}

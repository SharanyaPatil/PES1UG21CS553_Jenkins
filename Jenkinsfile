pipeline {
    agent any

    environment {
        SRN = "PES1UG21CS553" // Replace with your actual SRN
    }

    stages {
        stage('Build') {
            steps {
                script {
                    // Build command using environment variable for SRN
                    sh """
                        g++ -o ${env.SRN}-1 test.cpp || echo "Build failed!"
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Test command using the executable name
                    sh "./${env.SRN}-1"
                }
            }
        }
        stage('Deploy') {
            steps {
                // Add your deployment commands here
                echo 'Deployment not implemented yet.'
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed!"
        }
    }
}


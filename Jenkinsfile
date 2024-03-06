pipeline {
    agent any

    environment {
        // Optional: Set your SRN if you need to use it within the pipeline
        // SRN = "YOUR_SRN"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                   credentialsId: 'PES1202101779', # Replace with your credentials ID
                   url: 'https://github.com/SharanyaPatil/PES1UG21CS553_Jenkins' # Replace with your repository details
            }
        }
        stage('Build') {
            steps {
                script {
                    // Build command with warnings and error handling
                    sh """
                        g++ -o my_executable main.cpp -Wall -Wextra || echo "Build failed!"
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Test command using the executable name
                    sh './my_executable'
                }
            }
        }
        stage('Deploy') {
            steps {
                // Add your deployment commands here
                echo "Deployment not implemented yet."
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed!"
        }
    }
}

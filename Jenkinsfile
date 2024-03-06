pipeline {
    agent any
    stages {
        stage('Clone repository'){
          steps{
            checkout([$class: 'GitSCM',
            branches: [[name: '*/main']],
            userRemoteConfigs: [[url: 'https://github.com/SharanyaPatil/PES1UG21CS553_Jenkins']]])
          }
        }
        stage('Build') {
            steps {
                script {
                  build 'PES1UG21CS553'
                    sh 'g++ main.cpp -o output' 
                    
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh './OUTPUT'
                  
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    echo 'Deployment not implemented yet.'
                }
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed!"
        }
    }
}

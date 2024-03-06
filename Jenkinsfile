pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'mvn clean install' 
        echo'Build stage Successful'// Replace YOUR_SRN-1 with your actual file name.
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
         echo'Test stage Successful'
        post{
          always{
            junit 'target/surefire-reports/*.xml'
          }
        }
        // Change the command if your output is different.
      }
    }
    stage('Deploy') {
      steps{
        sh 'mvn deploy'
        echo 'Deployment Successful'
      // Add your deployment commands here (e.g., copy to server)
    }
    }
  }

  post {
    failure {
      echo 'Pipeline failed!'
    }
  }
}


pipeline {
  agent any

  environment {
    APP_NAME = "jenkins-practice"
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Build') {
      steps {
        sh 'bash scripts/build.sh'
      }
    }

    stage('Test') {
      steps {
        sh 'bash scripts/test.sh'
      }
    }

    stage('Deploy') {
      steps {
        sh 'bash scripts/deploy.sh'
      }
    }
  }

  post {
    success {
      echo "Pipeline completed successfully 🎉"
    }
    failure {
      echo "Pipeline failed ❌ Check logs!"
    }
  }
}

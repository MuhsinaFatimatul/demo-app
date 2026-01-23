pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/MuhsinaFatimatul/demo-app.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t demo-image:latest .'
      }
    }

    stage('Run Container') {
      steps {
        sh '''
          docker rm -f demo || true
          docker run -d --name demo -p 8081:80 demo-image:latest
        '''
      }
    }
  }
}

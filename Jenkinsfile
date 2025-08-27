pipeline {
  agent { label 'docker-builder' }  // runs on the Ubuntu builder
  environment {
    // Choose ONE registry. Example 1: Docker Hub
    
    IMAGE_NAME    = "nginx-app"
    TAG           = "${env.BUILD_NUMBER}"           // or a commit SHA
    FULL_IMAGE    = "${IMAGE_NAME}:${TAG}"
    }

  options {
    timestamps()
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
  }
    stage('Docker Build') {
      steps {
        sh '''
          echo "Building image: ${FULL_IMAGE}"
          docker build -t "${FULL_IMAGE}" .
        '''
      }
    }

    
}

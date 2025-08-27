pipeline {
  agent { label 'docker-builder' }  // runs on the Ubuntu builder

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

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

    
}

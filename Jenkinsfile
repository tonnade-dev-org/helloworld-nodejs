pipeline {
  agent {
        kubernetes {
          label 'nodejs-app-pod'
          yamlFile 'nodejs-pod.yaml'
        }
  }
  options { 
    buildDiscarder(logRotator(numToKeepStr: '3'))
    skipDefaultCheckout true
  }
  stages {
    stage('Test') {
      steps {
        checkout scm
        sh 'java -version'
        container('nodejs') {
          echo 'Hello World!'   
          sh 'node --version'
        } // container
      } // steps
    } // stage
    // CONDITIONAL STAGE
    stage('Build and Push Image') {
      when {
         beforeAgent true
         branch 'master'
      }
      steps {
         echo "TODO - build and push image"
      } // steps
    } // stage    
  } // stages
} // pipeline

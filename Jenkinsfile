pipeline {
  agent { label 'nodejs-app' }
  options { 
    buildDiscarder(logRotator(numToKeepStr: '3'))
    skipDefaultCheckout true
  }
  stages {
    stage('Test') {
      steps {
        sh 'java -version'
        container('nodejs') {
          echo 'Hello World!'   
          sh 'node --version'
        } // container
      } // steps
    } // stage
  } // stages
} // pipeline

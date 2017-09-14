pipeline {
  agent any
  stages {
    stage('initial') {
      steps {
        parallel(
          "initial": {
            sh 'echo "Hello"'
            
          },
          "initial2": {
            echo 'abc'
            
          }
        )
      }
    }
    stage('maven build') {
      steps {
        sh 'mvn clean'
      }
    }
  }
}
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
    stage('Deploy') {
            steps {
                retry(3) {
                    sh './flakey-deploy.sh'
                }

                timeout(time: 3, unit: 'MINUTES') {
                    sh './health-check.sh'
                }
            }
}
  }
}

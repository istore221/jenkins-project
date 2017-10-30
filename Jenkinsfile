pipeline {
  agent any

  stages {

    stage('build') {

        steps {
          sh 'env'
        }

    }

  }

  post {
    success {
      archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
    }
  }

}

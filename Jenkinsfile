pipeline {
  agent any

  stages {

    stage('build') {

        steps {
          sh 'echo test'
        }

    }

  }

  post {
    success {
      archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
    }
  }

}

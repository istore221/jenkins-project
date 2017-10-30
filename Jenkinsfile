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
    always {
      archiveArtifacts artifacts: '**/target/*.jar',onlyIfSuccessful: true , fingerprint: true
    }

  }

}

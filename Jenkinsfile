pipeline {
  agent any

  stages {

    stage('build') {

        steps {
          sh 'echo $PATH'
        }

    }

  }

  post {
    always {
      archiveArtifacts artifacts: '**/target/*.jar',onlyIfSuccessful: true , fingerprint: true
    }

  }

}

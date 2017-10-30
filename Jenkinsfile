pipeline {
  agent any

  stages {

    stage('build') {

        steps {
          sh 'mvn clean install'
        }

    }

  }

  post {
    always {
      archiveArtifacts artifacts: '**/target/*.jar',onlyIfSuccessful: true , fingerprint: true
    }

  }

}

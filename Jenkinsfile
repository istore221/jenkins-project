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
    success {
      archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
    }
  }

}

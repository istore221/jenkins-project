pipeline {
  agent any

  stages {

    stage('build') {

        steps {
          sh '/usr/local/bin/apache-maven-3.5.2/bin/mvn clean install'
        }

    }

  }

  post {
    always {
      archiveArtifacts artifacts: '**/target/*.jar',onlyIfSuccessful: true , fingerprint: true
    }

  }

}

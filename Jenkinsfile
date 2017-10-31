pipeline {
  agent any

  stages {

    stage('build') {

        steps {
          sh "/usr/local/bin/apache-maven-3.5.2/bin/mvn clean install"
        }

    }

  }

  post {
        success {
            archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
        }
  }



}

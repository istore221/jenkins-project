pipeline {
  agent any

  stages {

    stage('Unit Tests') {

        steps {
          sh "/usr/local/bin/apache-maven-3.5.2/bin/mvn test"
        }

    }

    stage('Build') {

        steps {
          sh "/usr/local/bin/apache-maven-3.5.2/bin/mvn clean install"
        }

    }

  }

  post {


        success {
            archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
        }

        always {
           junit '**/target/**/*.xml'
        }
  }



}

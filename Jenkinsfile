pipeline {
  agent any

  environment {
    MY_VERSION = '1.0.0'
  }

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

    stage('Merge Dev to Master') {

      when {
        branch 'dev'
      }

      steps {

        echo "git checkout master"
        echo 'git merge dev'
        echo 'git push origin master'
        echo 'git tag jenkins-project-${env.MY_VERSION}.${env.BUILD_NUMBER}'
        echo 'git push origin jenkins-project-${env.MY_VERSION}.${env.BUILD_NUMBER}'

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

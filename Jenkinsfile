pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        git(url: 'https://github.com/g-obasi/spring-petclinic.git', branch: 'main')
        withGradle() {
          sh './mvnw package'
        }

      }
    }

    stage('Execute Jar file') {
      steps {
        sh 'java -jar target/*.jar'
      }
    }

  }
}
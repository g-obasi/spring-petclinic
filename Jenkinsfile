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

    stage('Deploy Artifact on Prod server.') {
      steps {
        sh 'ansible-playbook Ansible_playbook.yml'
      }
    }

  }
}
pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            git(url: 'https://github.com/g-obasi/spring-petclinic.git', branch: 'main')
            withGradle() {
              sh './mvnw package'
            }

          }
        }

        stage('PWD and LS') {
          steps {
            sh 'pwd && ls'
          }
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
pipeline {
  agent any

    stages {
      stage('build') {
        steps {
          withCredentials([usernamePassword(
                SECRET: 'SECRET'
                )]) {
            // script {
            git branch: 'main',  url:  'https://github.com/sacrhamza/testing'
              sh './script'
              // }
          }
        }
      }
    }

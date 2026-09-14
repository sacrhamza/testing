pipeline {
  agent any

    stages {
      stage('Use Credentials') {
        steps {
          withCredentials([
              string(
                SECRET: 'SECRET',
                SOMETING: 'SECRET'
                )
          ])
          {
            sh '''
              echo "Username: $SECRET"
              touch "$SECRET"
              ls -l | wc
              '''
          }
        }
      }
    }
}

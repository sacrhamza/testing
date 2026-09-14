pipeline {
  agent any

    stages {
      stage('Use Credentials') {
        steps {
          sh '''
            echo "Username: $SECRET"
            touch "$SECRET"
            ls -l | wc
            '''
        }
      }
    }
}

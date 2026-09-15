pipeline {
  agent any
    stages {
      stage('build') {
        steps {
          sh 'error'
        }
      }
    }

  post {
    failure {
      emailext (
          subject: "BROKEN: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
          body: "Your commit broke the build. See details: ${env.BUILD_URL}",
          mimeType: 'text/html',
          recipientProviders: [
          tegabe3649@duidir.com      // Sends to the developers who committed code since the last stable build
          // requestor()      // Sends to the user who manually triggered the build (if applicable)
          ]
          )
    }
  }

}

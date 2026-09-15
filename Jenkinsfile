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
          subject: "Pipeline Failed: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
          body: """The pipeline failed on the last commit. 
          Check console output at: """,
          to: 'tegabe3649@duidir.com' // Sends email to the author of the change
          )
    }
  }
}

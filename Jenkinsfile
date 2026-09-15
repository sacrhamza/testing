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
      // add here all info about the build
      // attack output
          subject: "Pipeline Failed: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
          body: """The pipeline failed on the last commit. 
          Check console output at: """,
          recipientProviders: [culprits(), developers()],  // send to the commiter
          attachLog: true // This grabs the log file from Jenkins automatically
          )
emailext (
      // add here all info about the build
      // attack output
          subject: "Pipeline Failed: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
          body: """The pipeline failed on the last commit. 
          Check console output at: """,
          recipientProviders: [culprits(), developers()],  // send to the commiter
          attachLog: true // This grabs the log file from Jenkins automatically
          )
    }
  }
}

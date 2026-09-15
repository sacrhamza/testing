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
          to: 'culprits(), developers()' // Sends email to the author of the change
          )
    }
  }

// post {
//     failure {
//         emailext (
//             subject: "BROKEN: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
//             body: "Your commit broke the build. See details: ${env.BUILD_URL}",
//             mimeType: 'text/html',
//             recipientProviders: [
//                 culprits(),      // Sends to the developers who committed code since the last stable build
//                 developers(),    // Sends to everyone who committed code for this specific build
//                 requestor()      // Sends to the user who manually triggered the build (if applicable)
//             ]
//         )
//     }
// }
//
// }

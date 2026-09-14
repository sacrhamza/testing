// pipeline {
//   agent any
//
//     stages {
//       stage('build') {
//         steps {
//           withCredentials([usernamePassword(
//                 SECRET: 'SECRET'
//                 )]) {
//             // script {
//             git branch: 'main',  url:  'https://github.com/sacrhamza/testing'
//               sh './script'
//               // }
//           }
//         }
//       }
//     }
// }

// pipeline {
//     agent any
//
//     stages {
//         stage('Use Credentials') {
//             steps {
//                 withCredentials([usernamePassword(
//                     string(
//                      credentialsId: 'SECRET',
//                      variable: 'SECRET'
//                     )
//                 )]) {
//                     sh '''
//                         echo "Username: $SECRET"
//                         echo "Password: $SECRET"
//                     '''
//                 }
//             }
//         }
//     }
// }

pipeline {
    agent any

    stages {
        stage('Use Credentials') {
            steps {
                withCredentials([
                    string(
                        credentialsId: 'DISCORD_HOOK',
                        variable: 'DISCORD_HOOK'
                    )
                ]) {
                    sh '''
                    ./discord_send.sh
                    '''
                }
            }
        }
    }
}

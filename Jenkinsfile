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

pipeline {
    agent any
    
    stages {
        stage('Use Credentials') {
            steps {
                withCredentials([usernamePassword(
                SECRET: 'SECRET'
                    // credentialsId: 'MY_CREDENTIALS_ID',
                    // usernameVariable: 'USERNAME',
                    // passwordVariable: 'PASSWORD'
                )]) {
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

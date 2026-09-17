pipeline {
  agent any
    stages {
      stage ('add file') {
        steps  {
          withCredentials(
              [usernamePassword(
                credentialsId: 'Github-token',
                passwordVariable: 'GITHUB_TOKEN',
                usernameVariable: 'GIT_USERNAME')])
          {
            // git branch: 'testing', url: 'https://github.com/sacrhamza/testing.git'
            sh '''
              git checkout testing
              git branch
              echo "hello from jenkins" > newfile
              git add .
              git commit -m "jenkins commited"
              git push   
              git push https://${GIT_USERNAME}:${GITHUB_TOKEN}@github.com/sacrhamza/testing.git

              '''
          }
        }
      }
    }
}

pipeline {
  agent any
    stages {
      stage ('add file') {
        steps  {
          withCredentials(
              [
              usernamePassword(
                credentialsId: 'Github-token',
                passwordVariable: 'GITHUB_TOKEN',
                usernameVariable: 'GIT_USERNAME'),
                string (
                credentialsId: 'MAIL',
                variable: 'MAIL'
                )
              ]
            )
          {
           deleteDir()
           checkout scm
            // git branch: 'testing', url: 'https://github.com/sacrhamza/testing.git'
            sh '''
            ls
            # git fetch origin
             git branch
             git checkout testing
             git branch
             git status


              # do some changes
             echo "hello from jenkins" > newfile4

             git add .
             git commit -m 'jenkins commited'


              # config mail and username for git
             #git config user.email ${MAIL}
             #git config user.name ${GIT_USERNAME}

             git push https://${GIT_USERNAME}:${GITHUB_TOKEN}@github.com/${GIT_USERNAME}/testing.git
              '''
          }
        }
      }
    }
    post {
      success {
        echo 'pushed successfully'
      }
      failure {
        echo 'fail'
      }
    }
}

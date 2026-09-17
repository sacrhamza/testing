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
            // git branch: 'testing', url: 'https://github.com/sacrhamza/testing.git'
            sh '''
            ls
            # git fetch origin
             git branch
             git checkout testing
            # git reset --hard origin/testing
             git branch
             git status
              #git config pull.ff only 
             git pull
             git config user.email ${MAIL}
             git config user.name ${GIT_USERNAME}
             git branch
             echo "hello from jenkins" > newfile1
             git add .
             git commit -m 'jenkins commited'
             git push https://${GIT_USERNAME}:${GITHUB_TOKEN}@github.com/${GIT_USERNAME}/testing.git

              '''
          }
        }
      }
    }
}

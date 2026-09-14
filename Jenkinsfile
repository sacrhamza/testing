pipeline {
  agent {
    docker {
      image 'debian'
    }
  }

  stages {
    stage('build') {
      steps {
        script {
          git branch: 'main',
            url: 'https://github.com/sacrhamza/testing'
            sh 'apt update && apt install curl file -y'
            sh 'bash ./discord_send.sh'
        }
      }
    }
  }
}

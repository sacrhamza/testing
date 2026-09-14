pipeline {
  agent any

  stages {
    stage('build') {
      steps {
        script {
          git branch: 'main',  url:  'https://github.com/sacrhamza/testing'
          sh './script'
        }
      }
    }
  }
}

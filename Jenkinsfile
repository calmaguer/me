pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        bat(script: 'npm_install.bat', encoding: 'utf8')
      }
    }
  }
}
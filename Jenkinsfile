pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        bat(script: 'D:/Proyectos/DevOps/Jenkins/npm_install.bat', encoding: 'utf8')
      }
    }
    stage('Build') {
      steps {
        bat(script: 'D:/Proyectos/DevOps/Jenkins/npm_run_build.bat', encoding: 'utf8')
      }
    }
    stage('Test') {
      steps {
        bat(script: 'D:/Proyectos/DevOps/Jenkins/npm_test.bat', encoding: 'utf8')
      }
    }
  }
}
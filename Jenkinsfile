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
      parallel {
        stage('Test') {
          steps {
            bat(script: 'D:/Proyectos/DevOps/Jenkins/npm_test.bat', encoding: 'utf8')
          }
        }
        stage('Send Email') {
          steps {
            emailext(subject: 'Aprobar Paso', body: 'Favor de Aprobar ', attachLog: true, to: 'utester')
          }
        }
      }
    }
    stage('Aprove') {
      steps {
        input(message: 'Aprobar?', submitter: 'utester')
      }
    }
    stage('To Deploy') {
      steps {
        emailext(subject: 'Deploy', attachLog: true, body: 'Aprobar Deploy', to: 'urelease')
      }
    }
    stage('To Deploy A') {
      steps {
        input(message: 'Aprobar Deploy?', submitter: 'urelease')
      }
    }
  }
}
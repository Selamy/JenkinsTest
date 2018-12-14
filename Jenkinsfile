pipeline {
  agent {
    dockerfile {
      filename './Dockerfile'
    }
  }
  stages {
    stage('Git pull') {
      steps {
        git(url: 'https://github.com/Selamy/JenkinsTest', branch: 'master')
      }
    }
    stage('composer install') {
      steps {
        sh 'composer install'
      }
    }
    stage('Unit test') {
      agent {
        docker {
          image 'redislabs/rejson:latest'
            args '-p 6379:6379'
          }
      }
      steps {
        sh 'composer run unit-tests'
      }
    }
  }
}
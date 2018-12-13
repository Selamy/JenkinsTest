pipeline {
  agent {
    dockerfile {
      filename './Dockerfile'
      additionalBuildArgs "-p 6379:6379"
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
      steps {
        sh 'composer run unit-tests'
      }
    }
  }
}
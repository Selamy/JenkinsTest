pipeline {
  agent {
    docker {
      image 'zaherg/php-7.2-xdebug-alpine'
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
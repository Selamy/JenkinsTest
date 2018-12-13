pipeline {
  agent {
    docker {
      image 'phpdockerio/php72-cli'
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
            }
          }
          steps {
            sh 'composer run unit-tests'
          }
        }
  }
}
pipeline {
  agent {
    docker {
      image 'redislabs/rejson:latest'
    }
  }
  stages {
          agent {
            docker {
              image 'phpdockerio/php72-cli'
            }
          }
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
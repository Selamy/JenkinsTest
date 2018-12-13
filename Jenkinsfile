pipeline {
  agent any
  stages {
    stage('Git pull') {
      parallel {
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
        stage('Start docker') {
          steps {
            sh 'docker-compose up -d'
          }
        }
        stage('Unit test') {
          steps {
            sh 'composer run unit-tests'
          }
        }
      }
    }
  }
}
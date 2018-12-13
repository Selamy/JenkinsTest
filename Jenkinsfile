pipeline {
  agent {
    docker {
      dockerfile { dir './Dockerfile'}
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
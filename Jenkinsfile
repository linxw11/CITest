pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'start'
        bat 'gradle build'
      }
    }
    stage('ut') {
      steps {
        echo 'test'
      }
    }
    stage('package') {
      steps {
        echo 'package'
      }
    }
    stage('auto test') {
      parallel {
        stage('monkey') {
          steps {
            sleep 10
          }
        }
        stage('perform') {
          steps {
            sleep 10
          }
        }
        stage('replay') {
          steps {
            sleep 10
          }
        }
      }
    }
    stage('upload') {
      steps {
        sleep 10
      }
    }
    stage('release') {
      steps {
        sleep 10
      }
    }
  }
}
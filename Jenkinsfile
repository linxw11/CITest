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
        echo 'WORKSPACE'
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
        bat(script: 'curl -F \'file=@${WORKSPACE}/app/build/outputs/apk\' -F \'_api_key=44a037ad8e58e90ea0ee5285babb845b\' https://www.pgyer.com/apiv2/app/upload', returnStatus: true, returnStdout: true)
      }
    }
    stage('staging') {
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
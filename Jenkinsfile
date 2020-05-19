pipeline {
  agent any
  stages {
    stage('Hello Motherfucker') {
      parallel {
        stage('Hello Motherfucker') {
          steps {
            sh 'echo "What up daug?"'
          }
        }

        stage('Build this shit') {
          agent {
            docker {
              image 'gradle:jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

  }
}
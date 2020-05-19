pipeline {
  agent any
  stages {
    stage('Hello Motherfucker') {
      parallel {
        stage('Hello Motherfucker') {
          steps {
            sh 'echo "What up daug? This is parrellel"'
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
            sh 'echo "Just look how parallel we are"'
          }
        }

      }
    }

    stage('Going library') {
      steps {
        archiveArtifacts 'app/build/libs/'
      }
    }

  }
}
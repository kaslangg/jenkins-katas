pipeline {
  agent any
  stages {
    stage('Clone Down') {
      steps {
      stash excludes: '.git', name: 'code'
      }
    }
    stage('Hello Motherfucker') {
                
      parallel {
        stage('Hello Motherfucker') {
          steps {
            sh 'echo "What up daug? This is parrellel"'
          }
        }

        stage('Build this shit') {
          options {
            skipDefaultCheckout true
          }
          agent {
            docker {
              image 'gradle:jdk11'
            }
          }
          steps {
            unstash 'code'
            sh 'ci/build-app.sh'
            archiveArtifacts 'app/build/libs/'
            sh 'echo "Just look how parallel we are"'
          }
        }

      }
    }

  }
  }

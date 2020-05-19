pipeline {
  agent any
  stages {
    stage('Clone Down') {
      steps {
      stash excludes: '.git', name: 'code'
      }
    stage('Hello Motherfucker') {
      parallel {
        stage('Hello Motherfucker') {
          options {
                  skipDefaultCheckout true
                  }
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
            unstash 'code'
          }
          steps {
            sh 'ci/build-app.sh'
            archiveArtifacts 'app/build/libs/'
            sh 'echo "Just look how parallel we are"'
          }
        }

      }
    }

  }
}

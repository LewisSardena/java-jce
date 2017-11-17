pipeline {
  agent any

  options {
    buildDiscarder(logRotator(numTokeepStr: '2', artifactNumToKeepStr: '1'))
  }

  stages {
    stage('Build') {
      steps {
        sh 'ant -f build.xml -v'
        }
      }
    }

    post {
      always {
        archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
      }
    }
  }

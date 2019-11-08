pipeline {
  options {
    disableConcurrentBuilds()
  }
  agent {
    label "pkstest"
  }
  environment {
    DEPLOY_NAMESPACE = "jx-staging"
  }
  stages {
    stage('Validate Environment') {
      steps {
        container('pkstest') {
          dir('env') {
            sh 'jx step helm build'
          }
        }
      }
    }
  }
}

pipeline {
  options {
    disableConcurrentBuilds()
  }
  agent {
    label "jenkins"
  }
  environment {
    DEPLOY_NAMESPACE = "jx-staging"
  }
  stages {
    stage('Validate Environment') {
      steps {
        container('maven') {
        dir('env') {
            sh 'jx step helm build'
          }
        }
      }
    }
  }
}

pipeline {

  agent any

  stages {
    stage('checkout git') {
      steps {
        checkout([
        $class: 'GitSCM',
        userRemoteConfigs: [[url: 'https://github.com/hahsnejeb/jenkinstest1.git']]
        ])
        echo env.GIT_BRANCH
      }
    stage('build') {
      steps {
        echo 'Building...'
        cp Jenkinsfile Jenkinsfile.orig
      }
    }
    }
  }
}

pipeline {

  agent any

  stages {
    stage('checkout git') {
      steps {
        checkout([
        $class: 'GitSCM',
        userRemoteConfigs: [[url: 'git@github.com:hahsnejeb/jenkinstest1.git']]
        ])
        echo env.GIT_BRANCH
      }
    }

  }
}

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
    }
    stage('build') {
      steps {
        echo 'Building...'
        sh '/usr/local/bin/apache-maven-3.6.0/bin/mvn clean package'
        post {
          success {
            echo 'Now Archiving...'
            archiveArtifacts artifacts: '**/target/*.war'
          }
        }
      }
    }
  }
}

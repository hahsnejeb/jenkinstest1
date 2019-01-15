pipeline {

  agent any

  parameters {
    string(name: 'SCM', defaultsValue: 'https://github.com/hahsnejeb/maven-project.git', description: 'default git repo')

  stages {
    stage('package') {
      steps {
        echo 'packaging...'
        checkout([
        $class: 'GitSCM',
        branches: 'master',
        userRemoteConfigs: [[url: 'https://github.com/hahsnejeb/maven-project.git']]

      }
    }
    stage('test') {
      steps {
        echo 'testing...'
      }
    }
    stage('deploy-stage') {
      steps {
        echo 'deploying to stage...'
      }
    }
  }
}

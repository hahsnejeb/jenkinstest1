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
      }
    }
    stage('deployments') {
      parallel {
        stage('deploy-staging') {
          steps {
            echo 'Deploying Staging...'
            sh 'cp webapp/target/webapp.war  /usr/local/bin/apache-tomcat-7.0.92-staging/webapps/'
          }
        }
    
        stage('deploy-production') {
          steps {
            echo 'Deploying Production...'
            sh 'cp webapp/target/webapp.war  /usr/local/bin/apache-tomcat-7.0.92-production/webapps/'
          }
        }
      }
    }
  }
}

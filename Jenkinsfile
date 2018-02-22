pipeline {
  agent any
  stages {
    stage('Environments') {
      agent {
        node {
          label 'master'
        }
        
      }
      steps {
        libraryResource '../../.envvars/environments.groovy'
      }
    }
    stage('Build') {
      agent {
        node {
          label 'test'
        }
        
      }
      steps {
        sh 'mvn -version'
      }
    }
    stage('Deploy') {
      steps {
        waitUntil() {
          sh 'echo "deploying"'
        }
        
      }
    }
  }
}
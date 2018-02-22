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
        script {
          environment.set()
        }
        
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
        script {
          if ( true ) {
            print env.CURRENT_DEV_BRANCH
          }
        }
        
      }
    }
  }
}
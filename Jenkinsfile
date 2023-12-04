pipeline {
  agent any
  stages {
    stage('Verify validator installation') {
      steps {
        sh '''
          validator -version
          validator --help
        '''
      }
    }
    stage('Standard Run') {
      steps {
        sh 'validator org1 || true'
      }
    }
    stage('Multiple search paths') {
      steps {
        sh 'validator org1 org2 || true'
      }
    }
    stage('Exclude directories') {
      steps {
        sh 'validator --exlude-dirs org1/project02 org1 || true'
      }
    }
    stage('Exclude file types') {
      steps {
        sh 'validator --exclude-file-types=json org1 || true'
      }
    }
    stage('Customize recursion depth') {
      steps {
        sh 'validator --depth=1 org2 || true'
      }
    }
    stage('Customize report output') {
      steps {
        sh 'validator --reporter=json org1 || true'
      }
    }
  }
}

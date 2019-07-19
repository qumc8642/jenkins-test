pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        sh '''cd ../jenkins-test_master/pythonScripts

python3 AMICreatePython.py

'''
      }
    }
  }
}
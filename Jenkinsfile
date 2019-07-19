pipeline {
  agent any
  stages {
    stage('PythonAMIParser') {
      steps {
        sh '''sudo cd ~/../../../home/tduser/jenkinsPython
python3 AMICreatePython.py

'''
      }
    }
  }
}
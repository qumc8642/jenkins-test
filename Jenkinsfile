pipeline {
  agent any
  stages {
    stage('PythonAMIParser') {
      steps {
        sh '''cd ~/../../../
pwd
cd home/tduser/jenkinsPython
pwd
python3 AMICreatePython.py

'''
      }
    }
  }
}
pipeline {
  agent any
  stages {
    stage('PythonAMIParser') {
      steps {
        sh '''cd ~/../../../
pwd
sudo cd home/tduser/jenkinsPython
pwd
python3 AMICreatePython.py

'''
      }
    }
  }
}
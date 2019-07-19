pipeline {
  agent any
  stages {
    stage('PythonAMIParser') {
      steps {
        sh '''cd ~/../../../
pwd
cd home/tduser/
pwd
ls
cd jenkinsPython
python3 AMICreatePython.py

'''
      }
    }
  }
}
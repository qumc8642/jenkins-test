pipeline {
  agent any
  stages {
    stage('PythonAMIParser') {
      steps {
        sh '''cd ~/../../../
pwd
cd home/
ls
cd jenkinsPythonScript
python3 AMICreatePython.py
'''
      }
    }
  }
}
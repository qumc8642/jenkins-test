pipeline {
  agent any
  stages {
    stage('PythonAMIParser') {
      steps {
        sh '''sudo cd ~/../../../home/tduser
python3 jenkinsPython/AMICreatePython.py

'''
      }
    }
  }
}
pipeline {
  agent any
  stages {
    stage('PythonAMIParser') {
      steps {
        sh '''cd ~/../../../
cd home/
cd jenkinsPythonScript
python3 AMICreatePython.py
'''
        script {
          echo ${AMI_ID}
        }

      }
    }
  }
  parameters {
    string(name: 'AMI_ID', defaultValue: 'None', description: 'Enter an AMI_ID to boot up and test')
  }
}
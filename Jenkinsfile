pipeline {
  agent any
  parameters {
    string(name: 'AMI_ID',
    defaultValue: 'None',
    description: 'Enter an AMI_ID to boot up and test')
  }
  stages {
    stage('PythonAMIParser') {
      steps {
        echo "AMI_ID: ${params.AMI_ID}"
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

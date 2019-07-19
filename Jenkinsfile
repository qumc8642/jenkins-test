pipeline {
  agent any
  stages {
    stage('PythonAMIParser') {
      steps {
        sh '''cd ~/../../../
cd home/
cd jenkinsPythonScript'''
        script {
          echo "Entered AMI_ID: ${AMI_ID}"
          python "AMICreatePython.py ${AMI_ID}"
        }

      }
    }
  }
  parameters {
    string(name: 'AMI_ID', defaultValue: 'None', description: 'Enter an AMI_ID to boot up and test')
  }
}
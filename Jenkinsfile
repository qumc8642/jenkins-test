pipeline {
  agent any
  stages {
    stage('PythonAMIParser') {
      steps {
        sh '''echo Navigating to correct directory
cd ~/../../../
cd home/
cd jenkinsPythonScript
python3 AMICreatePython.py ${AMI_ID}'''
        script {
          echo "Entered AMI_ID: ${AMI_ID}"
        }

      }
    }
  }
  parameters {
    string(name: 'AMI_ID', defaultValue: 'None', description: 'Enter an AMI_ID to boot up and test')
  }
}
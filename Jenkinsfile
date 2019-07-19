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

        warnError(message: 'The instanceID given is not currently running on AWS', catchInterruptions: true) {
          echo 'Run Pipeline with parameters to enter an AMI'
        }

        catchError(buildResult: 'AMI ID NULL', message: 'The instanceID given is not currently running on AWS', stageResult: 'Fail') {
          echo 'Try running the pipeline with parameters and entering an AMI ID'
        }

      }
    }
  }
  parameters {
    string(name: 'AMI_ID', defaultValue: 'None', description: 'Enter an AMI_ID to boot up and test')
  }
}
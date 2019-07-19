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

        catchError(buildResult: 'SUCCESS', message: 'The AMI ID given does not match any preset images', stageResult: 'FAILED', catchInterruptions: true) {
          echo 'Try running the pipeline with parameters and entering an AMI ID'
        }

      }
    }
    stage('AMI Create') {
      steps {
        catchError(buildResult: 'FAIL', catchInterruptions: true, message: 'The AMI ID given does not match any preset images', stageResult: 'FAIL') {
          echo 'Run the process with parameters to enter the AMI ID'
        }

      }
    }
  }
  parameters {
    string(name: 'AMI_ID', defaultValue: 'None', description: 'Enter an AMI_ID to boot up and test')
  }
}
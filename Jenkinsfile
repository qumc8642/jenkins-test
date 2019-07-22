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
    stage('AMI Create') {
      steps {
        catchError(buildResult: 'FAILURE', catchInterruptions: true, message: 'The AMI ID given does not match any preset images', stageResult: 'FAILURE') {
          echo 'AMI Create Failed: Run the process with parameters to enter the AMI ID'
        }

      }
    }
    stage('test') {
      steps {
        echo 'test'
      }
    }
  }
  parameters {
    string(name: 'AMI_ID', defaultValue: 'None', description: 'Enter an AMI_ID to boot up and test')
  }
}
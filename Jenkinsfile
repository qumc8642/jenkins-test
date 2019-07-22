pipeline {
  agent any
  stages {
    stage('Create AMI') {
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
    stage('Test AMI') {
      steps {
        catchError(buildResult: 'SUCCESS', catchInterruptions: true, message: 'The AMI ID given does not match any preset images', stageResult: 'UNSTABLE') {
          echo 'AMI Create Failed: Run the process with parameters to enter the AMI ID'
        }

      }
    }
    stage('Log Results') {
      steps {
        echo 'test'
        s3Upload(file: 'test.txt', bucket: 'jenkins-log-scratch', path: '/', acl: 'BucketOwnerFullControl')
      }
    }
    stage('Deploy') {
      steps {
        catchError()
      }
    }
  }
  parameters {
    string(name: 'AMI_ID', defaultValue: 'None', description: 'Enter an AMI_ID to boot up and test')
  }
}
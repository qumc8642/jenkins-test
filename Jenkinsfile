pipeline {
  agent any
  stages {
    stage('Create AMI') {
      steps {
        sh '''#!/bin/bash

echo Navigating to correct directory
cd ~/../../../
cd home/
cd jenkins
ssh -i jenkins_ssh -tt tduser@54.172.42.112 \'

echo success

\'

'''
      }
    }
  }
  parameters {
    string(name: 'AMIId', defaultValue: 'None', description: 'Enter an AMI ID to boot up and test')
    string(name: 'InstanceType', defaultValue: 't2.micro', description: 'Enter an instance type ex: t2.micro, t2.small, etc..')
    string(name: 'DeployName', defaultValue: 'None', description: 'Enter a unique name for your instances, used for unique logging files')
  }
}
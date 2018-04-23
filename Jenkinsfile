pipeline {
  agent any
  stages {
    stage('Validate yaml') {
      steps {
        sh 'ansible-playbook plays/aws.build.playbook.yml  --syntax-check'
      }
    }
    stage('Test') {
      parallel {
        stage('Debian 9 ') {
          steps {
            sh  "sh ./os_factory aws debian_9 IMAGE_Base"
          }
        }
        stage('Ubuntu 16.04') {
          steps {
            sh  "sh ./os_factory aws ubuntu_16_04 IMAGE_Base"
          }
        }
        stage('Ubuntu 17.04') {
          steps {
            sh  "sh ./os_factory aws ubuntu_17_04 IMAGE_Base"
          }
        }
        stage('CentOS 7') {
          steps {
            sh  "sh ./os_factory aws centos_7 IMAGE_Base"
          }
        }
        stage('Windows 2012') {
          steps {
            sh  "sh ./os_factory aws windows_2012 IMAGE_Base"
          }
        }
        stage('Windows 2016') {
          steps {
            sh  "sh ./os_factory aws windows_2016 IMAGE_Base"
          }
        }
      }
    }
  }
}

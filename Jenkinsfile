pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                dir('ansible') {
                    git(
                      url: 'https://github.com/SviataslauDauhuchyts/ansible.git'
                      )
                }
            }
        }
        stage('Ansible') {
            steps {
              ansiColor('xterm') {
                ansiblePlaybook(
                  playbook: '$WORKSPACE/$JOB_NAME/ansible/test.yml',
                  inventory: '$WORKSPACE/$JOB_NAME/inventories/hosts',
                  colorized: true)
                }
            }
        }
        stage('Test') {
            steps {
                echo "Test stage"
            }
        }
    }
}

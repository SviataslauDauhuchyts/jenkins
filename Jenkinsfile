pipeline {
    agent any
    tools {
        terraform "terraform-0.11.3"
    }
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
                  playbook: '$WORKSPACE/ansible/test.yml',
                  inventory: '$WORKSPACE/ansible/inventories/jenkins/hosts',
                  colorized: true)
                }
            }
        }
        stage('Terraform') {
            steps {
                sh "terraform --version"
            }
        }
    }
}

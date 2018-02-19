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
                  playbook: '$WORKSPACE/ansible/test.yml',
                  inventory: '$WORKSPACE/ansible/inventories/jenkins/hosts',
                  colorized: true)
                }
            }
        }
        stage('Terraform') {
            steps {
                tools {
                    terraform "terraform-0.11.3"
                    sh "terraform --version"
                }
            }
        }
    }
}

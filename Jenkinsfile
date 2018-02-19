pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                dir('anible') {
                    git(
                      url: 'https://github.com/SviataslauDauhuchyts/ansible.git'
                      )
                }
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy stage"
            }
        }
        stage('Test') {
            steps {
                echo "Test stage"
            }
        }
    }
}

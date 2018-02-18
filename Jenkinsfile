pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git(
                  url: 'https://github.com/SviataslauDauhuchyts/ansible.git',
                  credentialsId: 'bf6b6502-60f0-4015-b59a-57b2881590ef'
                  )
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

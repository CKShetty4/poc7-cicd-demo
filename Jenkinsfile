pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/CKShetty4/poc7-cicd-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t poc7-demo .'
            }
        }

        stage('Deploy using Ansible') {
            steps {
                sh 'ansible-playbook -i ansible/inventory ansible/deploy.yml'
            }
        }
    }
}

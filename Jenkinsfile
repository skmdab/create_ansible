pipeline{

    agent any

    stages{
        stage('Checkout the code'){
            steps{
                git branch: 'main', credentialsId: 'git_token', url: 'https://github.com/skmdab/create_ansible.git'
            }
        }

        stage('Creating server'){
            steps{
                sh "sh aws_create.sh"
            }
        }

        stage('Installing ansible package into server'){
            steps{
                sh "ansible-playbook installansible.yaml"
            }
        }
    }
}
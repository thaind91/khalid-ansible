pipeline {

    agent{
        docker {
            alwaysPull true
            image 'khaliddinh/ansible'
        }
    }
    stages {

        stage('Deploy Mysql container') {
            steps {
                sh 'rm -rf .ssh'
                sh 'ls -la '
                sh 'cat Jenkinsfile'
                sh 'cat ansible_key'
                sh 'cat hosts'
                sh 'whoami'
                // sh 'ssh-keygen -b 2048 -t rsa -f .ssh/demo -q -N "" '
                // sh 'cp ansible_key .ssh/ansible_key'
                sh 'chmod 400 ansible_key'
                // sh 'ls -la .ssh'
                sh 'ansible --version '
                sh 'echo y | ansible all -m shell -i hosts --private-key ansible_key -a "echo $HOME" '
            }
        }
        
    }
}

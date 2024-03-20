pipeline {
    agent {
        label 'Ansible'
    }

    stages {
        stage('checout the playbook') {
            steps {
                git branch: 'main', credentialsId: 'webhook', url: 'https://github.com/gurumurthygd/Ansible-playbooks.git'
                
            }
        }
        stage('Excecute the playbook') {
            steps {
                ansiblePlaybook credentialsId: 'Ansibleserver', installation: 'Ansible', inventory: 'host.inv', playbook: 'create-user.yml', vaultTmpPath: ''
                
            }
        }
    }
}

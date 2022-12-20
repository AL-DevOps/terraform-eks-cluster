node('Terraform-Ansible') {
    stage('Checkout') { 
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub-user-password', url: 'https://github.com/AL-DevOps/terraform-eks-cluster.git']]])
    }
    
    stage('Terraform destroy') {
        sh '''terraform init
        terraform destroy --auto-approve'''
    }
    
    stage('Terraform apply') {
        sh '''terraform init
        terraform apply --auto-approve'''
    }
    stage(" execute Ansible version") {
        
    }   
    stage(" execute Ansible App") {
#        ansiblePlaybook credentialsId: 'ansible-andrey-key-frankfurt', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'host', playbook: 'playbook.yaml'
            
    } 
}

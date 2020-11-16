pipeline{
    agent any
    tools {
        terraform 'Terraform'
    }
    
    environment {
        AWS_ACCESS_KEY = credentials('AWS_ACCESS_KEY')
        AWS_SECRET_KEY = credentials('AWS_SECRET_KEY')
    }
    
    stages{
        stage("git checkout"){
            steps{
                git credentialsId: '8535c93d-f541-43dd-9e46-0b677efe7996', url: 'https://github.com/venkatpaik/devops_practice'
            }
        }
        stage("terraform init"){
            steps{
                sh label: 'tinit', script: 'terraform init'
            }
        }
        stage("terraform apply"){
            steps{
                sh label: 'tapply', script: 'terraform apply --auto-approve'
            }
        }
    }
}
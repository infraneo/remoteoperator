pipeline {
    agent any
    environment {
        HCLOUD_ACCESS_KEY = credentials('huawei_access_key')
        HCLOUD_SECRET_KEY = credentials('huawei_secret_key')
    }
    stages {
        stage('Verificar Dependencias') {
            steps {
                sh 'terraform --version'
                sh 'git --version'
            }
        }
        stage('Clonar Repositorio') {
            steps {
                git branch: 'main', url: 'https://github.com/TU-USUARIO/TU-REPO.git'
            }
        }
        stage('Inicializar Terraform') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Validar Configuración') {
            steps {
                sh 'terraform validate'
            }
        }
        stage('Aplicar Infraestructura') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}

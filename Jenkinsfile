pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
              checkout scmGit(branches: [[name: '*/develop']], extensions: [], userRemoteConfigs: [[credentialsId: '2f963125-c93e-4012-b6ed-e3e9a03e0dfd', url: 'https://github.com/ankit-bisaria/infra-case-study.git']]) 
               
            }
        }
    stage ("Terraform init"){
        steps {
            sh("terraform init");
        }
    }
    stage ("Terraform Action"){
        steps {
            echo "Terraform action parameter is --> ${action}"
            sh("terraform ${action} --auto-approve");
            
        }
    }
  }
}
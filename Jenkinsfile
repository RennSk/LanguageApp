pipeline {
    agent {
        kubernetes {
          label 'mykubeconfig'
        }
      }
    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/RennSk/LanguageApp.git'
            }
        }
        stage('Deploy to Minikube') {
            steps {
                script{
                    kubernetesDeploy(
                      configs: 'git.yaml',
                      kubeconfigId: 'mykubeconfig'
                    )
                }
            }
        }
    }
}

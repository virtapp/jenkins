pipeline {
    agent {
         any {
                 containerTemplate {
                   name 'helm'
                   image 'lachlanevenson/k8s-helm:v3.1.1'
                   ttyEnabled true
                  command 'cat'
              }
            }
         }
                     
    stages {
        stage('version cheak') {
            steps {
                sh 'helm version'
                sh 'kubectl version'
            }
        }
        stage('helm install simple-web'){
            steps{
                sh 'helm -n yevgeni ls'
                sh 'helm -n yevgeni delete --purge simple-web || true'
                sh 'helm -n yevgeni install simple-web simple-web'
            }
        }
    }
}

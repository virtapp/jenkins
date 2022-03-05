pipeline {
    agent {
        any {
            yaml '''
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: shell
    image: jayagrawaldocker/jenkins:0.4
    command:
    - sleep
    args:
    - infinity
'''
            defaultContainer 'shell'
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

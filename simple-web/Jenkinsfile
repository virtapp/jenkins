

def repo="https://github.com/virtapp/simple-web.git"
def path="/tmp/"

pipeline {
    agent any
    stages {
        stage("Clone Repository") {
                        steps {
                               sh "cd ${path}"
			       sh "rm -rf simple-web"
			       sh "git clone ${repo}"
			       sh "ls -la"
			       
                            }
                    }
				stage("Deploy") {
                        steps {
                            script{
					container('chart-deploy'){
                                        sh "helm upgrade simple-web simple-web -n yevgeni --wait"
                                    }
                                }
                            }
                    }
                
            }
        }

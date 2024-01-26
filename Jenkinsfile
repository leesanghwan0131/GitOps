pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/leesanghwan0131/GitOps.git will replace by sed command before RUN
        git url: 'https://github.com/leesanghwan0131/GitOps.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}
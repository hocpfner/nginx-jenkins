pipeline {

  agent { label 'kubepod' }
  /*
  tools {
    jdk 'Oracle-8u221'
  }
  */

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/hocpfner/nginx-jenkins.git', branch:'master'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}

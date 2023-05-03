pipeline {

  environment {
    dockerimagename = "nginx"
    dockerImage = ""
  }

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/mohzulfikar/test-kube-deploy.git'
      }
    }

    stage('Deploying nginx container to Kubernetes') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yaml", "service.yaml")
        }
      }
    }

  }

}

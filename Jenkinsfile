pipeline {
  environment {
    registry = "demo/whoami"
    registryUrl = "http://localhost:5000/"
  }
  agent any
  stages {
    stage('Building image') {
      steps{
        script {
           docker.withRegistry(registryUrl) {
                def customImage = docker.build(registry + ":${env.BUILD_ID}")
                customImage.push()
                customImage.push('latest')
           }
        }
      }
    }
  
  }
}

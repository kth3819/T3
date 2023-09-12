node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("kth3819/myrepo")
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'docker_key') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}

stage('Build image') {
  app = docker.build("kth3819/myrepo")
}

stage('Push image') {
  docker.withRegistry('https://registry.hub.docker.com', 'docker_key') 
  {
     app.push("${env.BUILD_NUMBER}")
     app.push("latest")
  }
}

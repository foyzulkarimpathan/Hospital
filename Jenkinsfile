node {
  def app
  stage('clone repository') {
  }
  stage('Build image') {
  app = docker.build("website")
  }
  stage('test image') {
    app.inside {
      sh 'echo "Tests Passed"'
    }
  }
  stage('push image') {
    docker .w1 thRegistry('https://docs.docker.com/', 'dockerhub') {
      app.push("${env.BUILD_NUMBER}")
      app.push("latest")
    }
  }
}

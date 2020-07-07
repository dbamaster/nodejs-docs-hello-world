pipeline {
  agent any
  stages {
    stage('Build') {
      agent any
      steps {
        sh '''docker build --tag helloworld:$BUILD_NUMBER .
docker stop helloworld && docker rm helloworld
docker run --name helloworld -p 1337:1337 helloworld:$BUILD_NUMBER node /var/www/index.js &'''
      }
    }

  }
}
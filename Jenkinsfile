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

    stage('Deliver') {
      steps {
        input 'Finished the CI part? (Click "Proceed" to continue)'
        sh 'echo "This is a test"'
      }
    }

  }
}
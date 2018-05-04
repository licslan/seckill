pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn clean'
        sh 'mvn install'
      }
    }
    stage('deliver') {
      steps {
        sh 'BUILD_ID=dontKillMe nohup java -jar seckill-0.0.1-SNAPSHOT.jar &'
        input 'Finished using the web site? (Click "Proceed" to continue)'
      }
    }
  }
}
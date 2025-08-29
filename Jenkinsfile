#!groovy

pipeline {
  agent any

  stages {
    stage('Setup Maven') {
      steps {
        sh '''
          if [ ! -d "apache-maven-3.8.6" ]; then
            echo "Downloading Maven 3.8.6..."
            wget -q https://archive.apache.org/dist/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz
            tar -xzf apache-maven-3.8.6-bin.tar.gz
            rm apache-maven-3.8.6-bin.tar.gz
          fi
          ./apache-maven-3.8.6/bin/mvn --version
        '''
      }
    }

    stage('Maven Install') {
      steps {
        sh './apache-maven-3.8.6/bin/mvn clean install'
      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -t grupo02/spring-petclinic:latest .'
      }
    }
  }
}

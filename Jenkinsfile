#!groovy

pipeline {
  agent any
  stages {
    stage('Maven Install') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('Docker Build') {
      steps {
        sh 'docker build -t grupo02/spring-petclinic:latest .'
      }
    }
  }
}

#!groovy

pipeline {
  agent none
  stages {
    stage('Maven Install') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t grupo02/spring-petclinic:latest .'
      }
    }
  }
}

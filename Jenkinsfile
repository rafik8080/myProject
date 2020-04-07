pipeline {
  agent { label 'master' }
  tools {
    maven 'maven-3.5.4'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/rafik8080/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}

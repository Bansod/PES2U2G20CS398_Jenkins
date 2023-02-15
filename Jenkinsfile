pipeline {
  agent any
  
  stages {
    stage('Clone') {
      steps {
        git branch: 'main', url: 'https://github.com/Bansod/PES2UG20CS398_Jenkins.git'
      }
    }
    
    stage('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    
    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }
    
    stage('Deploy') {
      steps {
        sh 'scp target/myapp.war user@remote-server:/opt/tomcat/webapps/'
      }
    }
  }
}

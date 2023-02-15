pipeline {
  agent any
  
  stages {
    stage('Build') {
      steps {
        sh 'g++ -o hello hello.cpp'
        echo 'Build stage successful.'
      }
    }
    
    stage('Test') {
      steps {
        sh './hello'
        echo 'Test stage successful.'
        post{
                    always{
                        junit 'target/surefire-reports/*.xml'
                    }
        }
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
  //post{
  //      failure{
   //         echo 'Pipeline failed'
   //     }
   // }
}

pipeline{
    agent any
    stages {
        stage('Build Stage'){

            steps{
                sh 'mvn clean install'
                echo 'Build stage successful.'
            }
        }
        stage('Test Stage'){
            steps{
                sh 'mvn test'
                echo 'Test stage successful.'
                post{
                    always{
                        junit 'target/surefire-reports/*.xml'
                    }
                }
            }
        }
        stage('Deploy Stage'){
            steps{
                sh 'mvn deploy'
                echo 'Deployment stage successful.'
            }
        }
    }
    post{
        failure{
            echo 'Pipeline failed.'
        }
    }
}

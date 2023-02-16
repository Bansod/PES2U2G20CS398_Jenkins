pipeline {
    agent any
    stages {
        stage('Build Stage') {
            steps {
                sh 'g++ -o PES2UG20CS398-1 hello.cpp'
                echo "Build Successful"
            }
        }
        stage('Test Stage') {
            steps {
                sh './PES2UG20CS466-1'
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}

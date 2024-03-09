pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                    build 'PES1UG21CS638-1'
                    sh 'g++ main1.cpp -o output'
            }
        }
        
        stage('Test') {
            steps {
                    sh './output'
            }
        }
        
        stage('Deploy') {
            steps {
                  echo "deploy"
            }
        }
      }
      post{
          failure{
            error 'pipeline failed'
          }
    }
}

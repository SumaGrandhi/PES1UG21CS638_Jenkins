pipeline {
    agent any
    
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/SumaGrandhi/PES1UG21CS638_Jenkins.git']]])
            }
        }
        
        stage('Build') {
            steps {
                sh 'g++ main1.cpp -o output'
                build 'PES1UG21CS638-1'
            }
        }
        
        stage('Test') {
            steps {
                sh './output'
                 script {
                    def output = sh(script: './output', returnStdout: true).trim()
                    echo "Output of main1.cpp: ${output}"
                }
            }     
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploy'
                //sh 'non_existent_command_failiure'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
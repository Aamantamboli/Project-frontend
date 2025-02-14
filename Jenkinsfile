pipeline {
    agent any 
    stages{
        stage('Pull'){
            steps{
                git branch: 'main', url: 'https://github.com/Aamantamboli/Project-frontend.git'
            }
        }
        stage('Build'){
            steps{
                sh '''
                    npm install 
                    ng build
                '''
            }
        }
        stage(''){
            steps{
                sh '''
                    aws s3 cp --recursive dist/angular-frontend/ s3://cbz-frontend1-project-bux/
                '''
            }
        }
    }
}
pipeline {
    agent any 
    environment{
        Vercel_Token = credentials('lawbb-vercel-orderhere-front-end')
    }
    
    stages {
        stage('Environment') {
            steps {
                sh 'npm install'
                sh 'npm start'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Test'){
            steps{
                sh 'node -v'
                sh 'npm run test'
            }
        }
        stage('Deploy'){
            steps{
              sh 'vercel --token = $Vercel_Token --prod --confirm'  
            }
            
        }
    }
}

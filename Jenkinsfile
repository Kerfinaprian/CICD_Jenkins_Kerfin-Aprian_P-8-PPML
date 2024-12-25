pipeline { 
   agent any

   environment {
       CI = 'true'
   }

   stages {
       stage('Checkout') {
           steps {
               git branch: 'main', url: 'https://github.com/Kerfinaprian/CICD_Jenkins_Kerfin_Aprian_P-8-PPML.git' 
           }
       }

       stage('Install Dependencies') {
           steps {
               bat 'npm install'
           }
       }

       stage('Run Unit Tests') {
           steps {
               bat 'npm test'
           }
       }

       stage('Build') {
           steps {
               echo 'Building the application...'
               
           }
       }

       stage('Deploy') {
           steps {
               echo 'Deploying the application...'
             
           }
       }
   }

   post {
       success {
           echo 'Pipeline finished successfully!' 
       }
       failure {
           echo 'Pipeline failed!'
       }
   }
}

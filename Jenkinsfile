pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Kerfinaprian/D_2200016030_Kerfin_Aprian_P-8-PPMPL.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Unit Tests') {
            steps {
                sh 'npm test'
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
        emailext subject: 'Build Succeeded',
                 body: 'The build was successful!',
                 recipientProviders: [[$class: 'DevelopersRecipientProvider']]
    }
    failure {
        emailext subject: 'Build Failed',
                 body: 'The build has failed.',
                 recipientProviders: [[$class: 'DevelopersRecipientProvider']]
    }
}

}
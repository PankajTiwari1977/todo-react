pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'sudo npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'sudo npm run build'
            }
        }
               stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-react-app:v1 .'
            }
        }
              stage('Push Docker Image') {
            steps {
                sh 'docker push pankajdevops2403/my-react-app:v1'
            }
        }        
}
}
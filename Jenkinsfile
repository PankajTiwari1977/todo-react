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

        stage('Test') {
            steps {
                sh 'sudo npm test -- --watchAll=false'
            }
        }

        stage('Serve (optional)') {
            steps {
                sh 'sudo npm install -g serve'
                sh 'sudo serve -s build -l 3000 &'
            }
        }
    }

    post {
        success {
            echo 'React app built and served successfully!'
        }
        failure {
            echo 'Build failed. Check the logs.'
        }
    }
}

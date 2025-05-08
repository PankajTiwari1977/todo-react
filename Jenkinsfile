// # jenkinsfile for a React application
// This Jenkinsfile is used to build, test, and deploy a React application using Docker and Kubernetes.
// It includes stages for installing dependencies, building the application, and deploying it to a Kubernetes cluster.
// The pipeline is defined using the declarative syntax and runs on any available agent.
// The pipeline is triggered by changes to the master branch of the Git repository.
// # trigger added

pipeline {
    agent any

    stages {
    //     stage('Install Dependencies') {
    //         steps {
    //             sh 'sudo npm install'
    //         }
    //     }

    //     stage('Build') {
    //         steps {
    //             sh 'sudo npm run build'
    //         }
    //     }
               stage('Build Docker Image') {
            steps {
                sh 'docker build -t pankajdevops2403/my-react-app:v2 .'
            }
        }
              stage('Push Docker Image') {
            steps {
                sh 'docker push pankajdevops2403/my-react-app:v2'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yml'
            }
        }        
}
}
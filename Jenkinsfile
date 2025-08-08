pipeline {
    agent any

    tools {
        nodejs "Node 20"  // match the name from Global Tool Configuration
    }

    environment {
        NODE_ENV = 'development'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Munhuu345/Nodejs_Project.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test' // or 'npm run test' depending on your script
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build' // if your project has a build step
            }
        }

        // Optional deployment stage
        // stage('Deploy') {
        //     steps {
        //         sh './deploy.sh' // or however you deploy
        //     }
        // }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // This can be removed when using "Pipeline script from SCM"
                echo 'Code checked out by Jenkins job SCM settings'
            }
        }

        stage('Build') {
            steps {
                echo 'Static HTML/CSS project - nothing to compile'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying portfolio to deployment folder...'
                bat '''
                if not exist "C:\\deploy\\portfolio-website" mkdir "C:\\deploy\\portfolio-website"
                xcopy * "C:\\deploy\\portfolio-website" /E /I /Y
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment successful 🎉'
        }
        failure {
            echo 'Deployment failed ❌'
        }
    }
}

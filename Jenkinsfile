pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'make -C main'
                echo 'Build stage completed'
            }
        }
        stage('Test') {
            steps {
                // Original command commented
                // sh 'cd main && ./hello_exec'

                // Intentional error
                sh 'cd main && ./error_exec'
                echo 'Test stage completed'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment stage'
                echo 'Application deployed successfully'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
        success {
            echo 'Pipeline succeeded'
        }
    }
}

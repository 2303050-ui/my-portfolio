
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Getting code from GitHub'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Checking HTML and CSS files'

                bat 'if exist index.html (echo HTML file found) else (exit /b 1)'

                bat 'if exist style.css (echo CSS file found) else (exit /b 1)'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'index.html,style.css'
            }
        }
    }

    post {
        success {
            echo 'Portfolio build successful!'
        }

        failure {
            echo 'Portfolio build failed!'
        }
    }
}

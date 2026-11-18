
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

                sh 'test -f index.html'
                sh 'test -f style.css'
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

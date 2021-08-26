pipeline {
    agent any
    stages {
        stage(‘build’) {
            steps {
                echo "Build stage..."
            }
        }
        stage(‘run’) {
            steps {
                echo "Run stage..."
            }
        }
    }
    post {
        success {
            echo "Post success...."
        }
    }
}

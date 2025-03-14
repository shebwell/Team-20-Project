pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git  url: 'https://github.com/shebwell/Team-20-Project.git',
                    credentialsId: 'da637548-59f7-43a8-b916-c4364fad15da',
                    branch: 'main'            }
        }
        stage('Build') {
            steps {
                sh 'mvn -e clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'sudo cp target/NumberGuessGame.war /var/lib/tomcat9/webapps/'
            }
        }
    }
    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

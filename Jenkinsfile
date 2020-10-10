pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out'
                git 'https://github.com/vigneshtraining/Expensetracker.git'
            }
        }
        stage('Compile') {
            steps {
                sh '/usr/bin/mvn compile'
            }
        }
        stage('test') {
            steps {
                sh '/usr/bin/mvn test'
            }
        }
        stage('package') {
            steps {
                sh '/usr/bin/mvn clean install'
            }
        }
        stage('deploy') {
            steps {
                dir('/var/lib/jenkins/workspace'){
                    sh './script.sh'
                }
            }
        }
        
    }
}

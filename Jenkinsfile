pipeline {
    agent any

    stages {
        stage('Initial Details') {
            steps {
                echo 'Initialization....'
                sh 'whoami'
                sh 'sudo chown -R jenkins .'
                sh 'ls -l'
                echo 'Initialization Complete'
            }
        }
        stage('Installing Dependencies') {
            steps {
                echo 'Installing....'
//                  sh 'sudo npm cache clean --force'
                 sh 'sudo npm install'
                echo 'Installation Complete'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'npm test -- --watchAll=false'
                echo 'Testing Complete'
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'sudo npm run build'
                echo 'Building Complete'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
    post{
        success{
            echo "====++++Successful++++===="
        }
        failure{
            echo "====++++Failed++++===="
        }
    }
    
}

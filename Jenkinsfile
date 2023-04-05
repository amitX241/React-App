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
        stage('Build') {
            steps {
                echo 'building....'
//                  sh 'sudo npm cache clean --force'
                 sh 'sudo npm install'
                echo 'build complete'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
    /*post{
        always{
            cleanWs()
        }
        success{
            echo "====++++only when successful++++===="
        }
        failure{
            echo "====++++only when failed++++===="
        }
    }*/
    
}

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'building....'
                sh 'sudo npm cache clean --force'
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

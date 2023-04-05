pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
//                 sh 'sudo npm cache clean'
//                 sh 'sudo npm install'
                echo 'building....'
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

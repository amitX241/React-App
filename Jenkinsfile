void setBuildStatus(String message, String state) {
    step([
      $class: "GitHubCommitStatusSetter",
      reposSource: [$class: "ManuallyEnteredRepositorySource", url: "https://github.com/amitX241/React-App.git"],
      contextSource: [$class: "ManuallyEnteredCommitContextSource", context: "ci/jenkins/build-status"],
      errorHandlers: [[$class: "ChangingBuildStatusErrorHandler", result: "UNSTABLE"]],
      statusResultSource: [ $class: "ConditionalStatusResultSource", results: [[$class: "AnyBuildResult", message: message, state: state]]]
  ]);
}

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
//                 sh 'sudo npm run build'
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
            setBuildStatus("Build succeeded", "SUCCESS");
//             sh "npm start"
        }
        failure{
            echo "====++++Failed++++===="
            setBuildStatus("Build failed", "FAILURE");
        }
    }
}

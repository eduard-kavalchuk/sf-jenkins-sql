pipeline {
    agent any
    triggers {
        pollSCM ''
    }
    stages {
        stage('Print hello world') {
            steps {
                echo 'Hello, world!'
            }
        }
    }
}
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    if (params.gitBranch == 'main') {
                        git branch: 'main', url: 'https://github.com/Deeba2020/Automatiserad-testning-Labb-Jenkins.git'
                    } else {
                        git branch: 'b1', url: 'https://github.com/Deeba2020/Automatiserad-testning-Labb-Jenkins.git'
                    }
                }
            }
        }
    }
}



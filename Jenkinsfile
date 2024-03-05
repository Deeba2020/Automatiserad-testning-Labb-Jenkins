pipeline {
    agent any

   

    stages {
        stage('Checkout') {
            steps {
                script {
                    if (params.gitBranch == 'main') {
                        git checkout('https://github.com/Deeba2020/Automatiserad-testning-Labb-Jenkins.git', branch: 'main')
                    } else {
                        git checkout('https://github.com/Deeba2020/Automatiserad-testning-Labb-Jenkins.git', branch: 'b1')
                    }
                }
            }
        }
    }
}

pipeline {
    agent any


     parameters {
        choice(description: 'Select a GitHub branch:', name: 'selectedBranch', choices: 'main\b1')
    }

    environment {
        GIT_CREDENTIALS = credentials('github-token')
    }

    stages {
        stage('Checkout') {
            steps {

                script{
                    if (params.selectedBranch== main){
                        git url: 'https://github.com/Deeba2020/Automatiserad-testning-Labb-Jenkins/tree/main', branch: 'main', credentialsId: GIT_CREDENTIALS
                    } else {
                        git url: 'https://github.com/Deeba2020/Automatiserad-testning-Labb-Jenkins/tree/b1', branch: 'main', credentialsId: GIT_CREDENTIALS
                    }

                }

            }
        }

     
    }
}


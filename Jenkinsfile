pipeline {
    agent any

    environment {
        GIT_CREDENTIALS = credentials('github-token')
    }

      stages{
        stage('Checkout') {
            steps {

                script{
                    if (params.gitBranch == 'main'){
                        git checkout( url: 'https://github.com/Deeba2020/Automatiserad-testning-Labb-Jenkins/tree/main', branch: 'main', credentialsId: GIT_CREDENTIALS)
                    } else {
                        git checkout(url: 'https://github.com/Deeba2020/Automatiserad-testning-Labb-Jenkins/tree/b1', branch: 'b1', credentialsId: GIT_CREDENTIALS)
                    }

                }

            }
        }
      }

     
}



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

         stage('Build') {
            steps {
                bat 'mvn -f "D:/GitProjects/Automatiserad0testning08030Labb0Jenkins/LabbJenkins/TrialRunnerTDD/pom" compile'

            }
        }

        stage('Test') {
            steps {
                bat "mvn test"
            }

            post {
                always {
                    jacoco(
                        execPattern: 'target/*.exec',
                        classPattern: 'target/classes',
                        sourcePattern: 'src/main/java',
                        exclusionPattern: 'src/test*',
                    )
                    junit '**/TEST*.xml'
                }
            }
        }

    }
}



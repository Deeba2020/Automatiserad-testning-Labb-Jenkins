pipeline {
    agent any

    stages {
        stage('BranchCheckout') {
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

        stage('BuildTrailRunner') {
            steps {
                bat 'mvn -f "D:\\GitProjects\\Automatiserad testningLabbJenkins\\LabbJenkins\\TrialRunnerTDD\\pom.xml" compile'
            }
        }

        stage('TestTrailRunner') {
            steps {
                bat 'mvn -f "D:\\GitProjects\\Automatiserad testningLabbJenkins\\LabbJenkins\\TrialRunnerTDD\\pom.xml" test'
            }
        }

        stage('TestResultTrailRunner') {
            steps {
                script {
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

        stage('RunRobot') {
            steps {
                script {
                    bat 'robot "D:\\GitProjects\\Automatiserad testningLabbJenkins\\LabbJenkins\\Selenium\\SeleniumLab1.robot"'
                }

                post {
                    always {
                        
                        robot (
                            outputPath: 'C:\\Users\\Administrator\\.jenkins\\workspace\\Deba\\output.xml',
                           
                        )
                    }

                 }
               
            }
        }
    }
}

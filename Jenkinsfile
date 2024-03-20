
pipeline {
    agent any

    stages {
        stage('BranchUsed') {
            steps {
                script {
                    if (params.branch == 'origin/b1') {
                        echo 'Checked out to the b1 branch'
                    } else {
                        echo 'Checked out to the main branch'
                    }
                }
            }
        }

        stage('BuildTrailRunner') {
            steps {
                bat 'mvn -f "C:\\Users\\Administrator\\.jenkins\\workspace\\Deba\\pom.xml" compile'
            }
        }

        stage('TestTrailRunner') {
            steps {
                bat 'mvn -f "C:\\Users\\Administrator\\.jenkins\\workspace\\Deba\\pom.xml" test'
            }
        }

        stage('TestResultTrailRunner') {
            steps {
                script {
                    jacoco(
                        execPattern: 'target/*.exec',
                        classPattern: 'target/classes',
                        sourcePattern: 'src/main/java',
                        exclusionPattern: 'src/test*'
                    )
                    junit '**/TEST*.xml'
                }
            }
        }

        stage('RunRobotTest') {
            steps {
                script {
                    bat 'robot "C:\\Users\\Administrator\\.jenkins\\workspace\\Deba\\AutomatiseradTestningLabb1\\SeleniumLab1.robot"'
                }
            }
        }
    }

    post {
        always {
            script {
                robot (
                    outputPath: 'C:\\Users\\Administrator\\.jenkins\\workspace\\Deba'
                )   
            }
        }
    }
}

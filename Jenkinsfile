pipeline {
    agent any

    stages {


        stage('branchUsed') {
            steps {
                script {
                    if (params.branch == 'main') {
                        echo 'Checked out main branch'
                    } else {
                        echo 'Checked out b1 branch'

                    }
                }
            }
        }

        stage('BuildTrailRunner') {
            steps {
                bat 'mvn -f "D:\\GitProjects\\Automatiserad testningLabbJenkins\\LabbJenkins\\TDDprojectJenkins\\pom.xml" compile'
            }
        }

        stage('TestTrailRunner') {
            steps {
                bat 'mvn -f "D:\\GitProjects\\Automatiserad testningLabbJenkins\\LabbJenkins\\TDDprojectJenkins\\pom.xml" test'
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
                    bat 'robot "D:\\GitProjects\\Automatiserad testningLabbJenkins\\LabbJenkins\\AutomatiseradTestningLabb1\\SeleniumLab1.robot"'
                }
            
            }
        }

        stage('PostRobotTest') {
            steps {
                script {
                    robot (
                        outputPath: 'C:\\Users\\Administrator\\.jenkins\\workspace\\Deba'
                    )   
                }
            }
        }

    }
}

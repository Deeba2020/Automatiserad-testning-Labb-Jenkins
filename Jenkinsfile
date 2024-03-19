pipeline {
    agent any

    stages {

        stage('BranchCheckout') {
            steps {
                script {
                  checkout scmGit(branches: [[name: '*/main'], [name: '*/b1']], extensions: [], userRemoteConfigs: [[]])

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

        stage('RunRobot') {
            steps {
                script {
                    bat 'robot "D:\\GitProjects\\Automatiserad testningLabbJenkins\\LabbJenkins\\AutomatiseradTestningLabb1\\SeleniumLab1.robot"'
                }
            
            }
        }

        stage('PostRobot') {
            steps {
                robot (
                    outputPath: 'C:\\Users\\Administrator\\.jenkins\\workspace\\Deba'
                )   
            
            }
        }
            

    
    }
}

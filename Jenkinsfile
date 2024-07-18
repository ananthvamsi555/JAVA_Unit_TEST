pipeline{
    agent any 
    tools {
        maven 'Maven'
    }
    stages{
        stage("Clone repository"){
            steps{
                git 'https://github.com/ananthvamsi555/JAVA_Unit_TEST.git'
            }
        }
        stage("Build"){
            steps{
                bat 'mvn clean package'        
            }
        }
    }
}

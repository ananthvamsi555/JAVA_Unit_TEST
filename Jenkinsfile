
pipeline{
    agent any 
    tools {
        maven 'Maven'
    }
    environment{
        REPO_URL = 'https://github.com/ananthvamsi555/JAVA_Unit_TEST.git'
        BRANCH = 'main'
        MVN_GOALS = 'Clean package'
        POM_FILE = 'pom.xml'
    }
    stages{
        stage("Clone repository"){
            steps{
                scmCheckout(REPO_URL,BRANCH)
            }
        }
        stage("Build"){
            steps{
                mavenBuild(MVN_GOALS,POM_FILE)        
            }
        }
    }
}

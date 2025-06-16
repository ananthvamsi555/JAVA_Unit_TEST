@Library('jenkins-shared-library') _
pipeline{
    agent any 
    tools {
        maven 'Maven'
    }
    environment{
        repoUrl = 'https://github.com/ananthvamsi555/JAVA_Unit_TEST.git'
        branch = 'master'
        MVN_GOALS = 'clean package'
        POM_FILE = 'pom.xml'
    }
    stages{
        stage("Clone repository"){
            steps{
                scmCheckout(repoUrl,branch)
            }
        }
        stage("Build"){
            steps{
                mavenBuild(MVN_GOALS,POM_FILE)        
            }
        }
    }
    post{
        success{
            archiveArtifacts artifacts: '**/target/**/*', allowEmptyArchive: true
        }
        always{
            junit '**/target/surefire-reports/*.xml'
        }
    }
}

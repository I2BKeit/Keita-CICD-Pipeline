pipeline {
    agent any
    tools {
        maven "maven"

    }
   
    stages{
        stage("Build"){
            steps{
                sh 'mvn clean install package'
            }
        }
       
        stage('Test'){
            steps{
                echo 'testing'
            }
        }
        stage('Publish the artifact to Nexus'){
            steps{
                sh 'mvn deploy'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying'
            }
        }
    }
}

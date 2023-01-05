pipeline {
    agent any
    tools {
        maven "maven"

    }
    environment {
        name= "keita Ibrehima"
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
                echo "By '${name}'"
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

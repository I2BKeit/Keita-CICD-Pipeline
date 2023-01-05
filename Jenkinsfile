pipeline {
    agent any
    tools {
        maven "maven"

    }
    environment {
        name= "keita Ibrehima"
        Version= readMavenPom().getVersion()
    }
   
    stages{
        stage("Build"){
            steps{
                sh 'mvn clean install package'
                echo " the version is '${Version}'"
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

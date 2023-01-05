pipeline {
    agent any
    tools {
        maven "maven"

    }
    environment{
        ArtifactId = readMavenPom().getArtifactId()
        Version = readMavenPom().getVersion()
        Name = readMavenPom().getName()
    }
    stages{
        stage("Build"){
            steps{
                sh 'mvn clean install package'
            }
        }
        stage("show informations"){
            steps{
                echo " Artifactifact is '${ArtifactId}'"
                echo "version is : '${version}'"
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

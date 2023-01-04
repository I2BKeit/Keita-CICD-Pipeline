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
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.4-SNAPSHOT.war', type: 'war']], credentialsId: '', groupId: 'com.vinaysdevopslab', nexusUrl: '10.0.0.73:8081', nexusVersion: 'nexus2', protocol: 'http', repository: 'keita-devops-snapshot', version: '0.0.4-SNAPSHOT'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying'
            }
        }
    }
}

pipeline{
    agent any

    stages{
        stage('Cloning GitHub Repository to Jenkins Server'){
            steps{
                script{
                    echo 'Cloning GitHub Repo to Jenkins ................'
                    checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/noamessi07/MLOPS-Projects.git']])
                }
            }
        }
    }
}
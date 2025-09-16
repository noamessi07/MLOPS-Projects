pipeline{
    agent any

    environment{
        VENV_DIR = 'venv'
    }

    stages{
        stage('Cloning GitHub Repository to Jenkins Server'){
            steps{
                script{
                    echo 'Cloning GitHub Repo to Jenkins ................'
                    checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/noamessi07/MLOPS-Projects.git']])
                }
            }
        }

        stage('Setting up our Virtual Environment and Installing Dependencies'){
            steps{
                script{
                    echo 'Setting up our Virtual Environment and Installing Dependencies ................'
                    sh '''
                    python -m venv ${VENV_DIR}
                    . ${VENV_DIR}/bin/activate}
                    pip install --upgrade pip
                    pip install -e .
                    '''
                }
            }
        }
    }
}
pipeline {
    agent {label 'Belkind-Agent'}
    stages {
        stage('Get Sources') {
            steps {
                git 'https://github.com/belkind27/ci-cd-test.git'
            }
        }
        stage('Restore Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') { 
            steps {
                sh 'npm run test' 
            }
        }
        stage('Package') { 
            steps {
                sh 'npm run build' 
            }
        }
        stage('Archive Artifacts') { 
            steps {
                archiveArtifacts '*.zip'
            }
        }
    }
}

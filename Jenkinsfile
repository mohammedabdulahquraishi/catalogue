pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        packageVersion = ''
    }
    stages {
        stage('Get the version') {
            steps {
                script {
                    def packageJson = readJSON file: 'package.json'
                    packageVersion = packageJson.version
                    echo "application version: $packageVersion"
                }
            }
        }
        stage('Install Dependencies') {
            steps {
                sh """ 
                npm install
                """
            }
        }
        stage('Build') {
            steps {
                sh """ 
                ls -la
                zip -q -r catalogue.zip ./* -x ".git" -x "*.zip"
                """
            }
        }
    }
}

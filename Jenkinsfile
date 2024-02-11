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
    }
}
pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        packageVersion = ''
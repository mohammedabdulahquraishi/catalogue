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
                    def packagejson = readJSON file: 'package.json'
                    packageVersion = packagejson.version
                    echo "application version: ${packgeVersion}"
                }
            }
        }
    }
}
pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
        stage('Pre-Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
        stage('Build') {
            steps {
                sh 'mvn --version'
            }
        }
    }
}
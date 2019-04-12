pipeline {
    agent { docker { image 'maven:3.3.3' } }

    environment {
        GLOBAL_VAR = 'true'
    }

    stages {

        stage('Pre-Build') {

            environment {
                PREBUILD_VAR = 'YES'
            }

            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                //Both GLOBAL_VAR and PREBUILD_VAR are available
                sh 'printenv'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn --version'
                 //Only PREBUILD_VAR are available
                sh 'printenv'
            }
        }

        stage('Pre-Deploy') {
            steps {
                retry(3) {
                    sh './flakey-deploy.sh'
                }

                timeout(time: 4, unit: 'SECONDS') {
                    sh './health-check.sh'
                }
            }
        }

//         stage('Fake-Faile-Stage') {
//            steps {
//                sh 'echo "Fail!"; exit 1'
//            }
//        }
    }

    post {

        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }

    }
}
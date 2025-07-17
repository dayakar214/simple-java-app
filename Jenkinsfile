pipeline {
    agent any

    stages {
        stage('Clone and Build') {
            stages {
                stage('Clone Repository') {
                    steps {
                        git url: 'https://github.com/dayakar214/simple-java-app.git', branch: 'main'
                    }
                }
                stage('Build') {
                    steps {
                        sh 'mvn clean package'
                    }
                }
            }
        }

        stage('Parallel Testing') {
            parallel {
                stage('Test Environment A') {
                    steps {
                        echo 'Running tests in Environment A...'
                        // sh './run-tests-A.sh'
                    }
                }

                stage('Test Environment B') {
                    steps {
                        echo 'Running tests in Environment B...'
                        // sh './run-tests-B.sh'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // sh './deploy.sh'
            }
        }
    }
}

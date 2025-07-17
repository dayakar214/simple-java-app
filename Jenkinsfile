pipeline {
    agent none

    stages {
        stage('Build on Dev') {
            agent { label 'dev' }
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

        stage('Test on Prod') {
            agent { label 'prod' }
            steps {
                echo 'Running tests on prod agent...'
                // You can run test commands here if needed
            }
        }

        stage('Deploy') {
            agent any
            steps {
                echo 'Deploying the application...'
                sh 'mkdir -p /tmp/deploy && cp target/*.jar /tmp/deploy/'
            }
        }
    }
}

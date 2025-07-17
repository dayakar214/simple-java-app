pipeline {
    agent none

    stages {
        stage('Clone') {
            agent { label 'dev' }
            steps {
                git 'https://github.com/spring-projects/spring-petclinic'
            }
        }

        stage('Build') {
            agent { label 'dev' }
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Deploy') {
            agent { label 'prod' }
            steps {
                echo 'Deploying to prod server...'
                // you can run scp, ssh, or other deploy logic here
            }
        }
    }
}

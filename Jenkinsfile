pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'maven:3-alpine'
                    args '-v /root/.m2:/root/.m2'
                }
            }
            steps {
                sh 'docker rmi my-app:latest'
                echo 'rm image successfully'
                sh 'mvn -B -DskipTests clean package dockerfile:build'
            }
        }
    }
}

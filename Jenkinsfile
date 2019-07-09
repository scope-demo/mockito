pipeline {
    agent none
    stages {
        stage('Build') {
            agent { docker 'openjdk:8-jdk' }
            steps {
                sh './gradlew build'
            }
        }
    }
}

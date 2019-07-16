pipeline {
    agent none
    stages {
        stage('Build') {
            agent { docker 'openjdk:8-jdk' }
            steps {
                sh './gradlew cleanTest test --rerun-tasks'
            }
        }
    }

    post {
        always {
            node('master') {
                 archiveArtifacts artifacts: '**/scope_*.log'
                 sh 'rm -f scope_*.log'
            }
        }
    }
}

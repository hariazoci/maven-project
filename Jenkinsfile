pipeline {
    agent {
        label 'ubuntu-git'
    }

    parameters {
        choice choices: ['dev', 'prod'], name: 'select_environment'
    }

    environment {
        NAME = "HariKrishna"
    }
    
    tools {
        maven 'mymaven'
    }

    stages {
        stage('build') {
            steps {
                sh 'mvn clean package -DskipTests=true'
            }
            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
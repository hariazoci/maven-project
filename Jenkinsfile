pipeline {
    
    agent {
        label 'ubuntu-git'
    }

    tools {
  maven 'mymaven'
}

    stages {
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}

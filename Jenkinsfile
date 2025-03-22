pipeline {
    
    agent {
        label 'ubuntu-git'
    
    }

    parameters {
  string defaultValue: 'beerangi', name: 'LASTNAME'
}

environment{
    NAME = "HariKrishna"
}
    tools {
  maven 'mymaven'
}

    stages {
        stage('build') {
            steps {
                sh 'mvn clean package'
                echo "hello $NAME" ${params.LASTNAME}
            }
            post {
                success {
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}

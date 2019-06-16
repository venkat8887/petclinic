pipeline {
    agent any 
    tools {
        maven 'M3' 
        jdk 'java8'
    }
    parameters { string(name: 'DEPLOY', defaultValue: 'no', description: '') }
    stages {
        stage('Build') { 
            steps {
              sh 'mvn clean package'
            }
        }
        stage('archive') {
            when {
                DEPLOY = "yes"
            }
            steps {
                 archiveArtifacts 'target/*.?ar'
            }
        }
        stage('junit') { 
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}

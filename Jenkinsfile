pipeline {
    agent any 
     tools {
        maven 'M3' 
        JDK 'java8'
    }
    stages {
        stage('Build') { 
            steps {
            
              sh 'mvn clean package'
                
            }
        }
        stage('archive') { 
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

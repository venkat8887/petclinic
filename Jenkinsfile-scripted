node('master') { 
	stage('build') {
		withEnv(["PATH+JAVA=${tool 'java8'}/bin"]) {
			withEnv(["PATH+MAVEM=${tool 'M3'}/bin"]){
				sh label: '', script: 'mvn clean package'
			}
		}
	}
	stage('archive') {
    archiveArtifacts 'target/*.?ar'
junit 'target/surefire-reports/*.xml'
}
}

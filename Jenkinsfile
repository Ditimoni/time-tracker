pipeline {
    agent any 
    stages {
	stage('checkout') {
		steps{
    		git 'https://github.com/Ditimoni/time-tracker.git'
	}
    	}
        stage('build and test') {
steps{
    		bat 'mvn clean package'
   	}
}
        stage('Deploy') { 
steps{
                  deploy adapters: [tomcat9(credentialsId: 'tomcat-manager-scripts', path: '', url: 'http://localhost:9080')], 
contextPath: '/demo', war: '**/*.war'
        }
}
   } 
}

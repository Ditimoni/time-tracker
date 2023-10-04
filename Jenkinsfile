pipeline {
    agent any 
    stages {
	stage('checkout') {
    		git 'https://github.com/Ditimoni/time-tracker.git'
    	}
        stage('build and test') {
    		bat 'mvn clean package'
   	}
        stage('Deploy') { 
                  deploy adapters: [tomcat9(credentialsId: 'tomcat-manager-scripts', path: '', url: 'http://localhost:9080')], 
contextPath: '/demo', war: '**/*.war'
        }
    }
}

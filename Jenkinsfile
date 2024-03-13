pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/avinash/Downloads/tar2-file/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/myntra.war /home/virat/appfile/apache-tomcat-9.0.85/webapps'
			}} 
		stage('slack-notification') {
			steps{
				 slackSend baseUrl: 'slackSend channel: \'devops\', color: \'good\', teamDomain: \'student\', tokenCredentialId: \'slacktest\'/', channel: 'devops', color: 'good', teamDomain: 'student', tokenCredentialId: 'slacktest'  
			}}
 


 }}	




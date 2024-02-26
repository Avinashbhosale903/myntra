pipeline {
	agent any 
	
	triggers {
  pollSCM '* * * * *'
}
	parameters {
  choice choices: ['DEV', 'QA', 'UAT'], name: 'environment'
}
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
		sh 'cp target/myntra.war /home/avinash/Downloads/tar2-file/apache-tomcat-9.0.85/webapps'
			}}
		stage('slack-notification'){
		   steps {
		     
		     slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#devops', color: 'good', message: 'This is for test', teamDomain: 'student', tokenCredentialId: 'slacktest'
		     }}	


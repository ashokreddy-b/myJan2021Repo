pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	stages{
		stage('Build'){
			steps
			{
				sh 'mvn clean install'	
			}
			
		}
		stage('Deploy to tomcat server')
		{
			steps{
				deploy adapters: [tomcat9(credentialsId: 'f51a5985-0eb3-4c93-b246-f8ff0763b8cb', path: '', url: 'http://ec2-35-78-239-61.ap-northeast-1.compute.amazonaws.com:8080/ ')], contextPath: null, war: 'target/*.war'
			}	
		}
	}
}

pipeline{
	agent{label 'slave'}
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
				deploy adapters: [tomcat9(credentialsId: '72c13c38-4a76-4279-b546-d68fb100f418', path: '', url: 'http://ec2-35-78-239-61.ap-northeast-1.compute.amazonaws.com:8080/')], contextPath: null, war: 'target/*.war'
			}	
		}
	}
}

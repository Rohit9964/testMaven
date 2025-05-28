pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	
	stages{
		stage('checkout'){
			steps{
				git branch : 'master', url : 'https://github.com/Rohit9964/testMaven.git'
			}
		}
		stage('build'){
			steps{
				sh 'mvn clean install'
			}
		}
		
		stage('test'){
			steps{
				sh 'mvn test'
			}
		}
		stage('Run Application'){
			steps{
				sh 'java -jar target/lab2MavenApp-1.0-SNAPSHOT.jar'		
			}
		}
	}
	post{
		success{
			echo 'build successful'
		}
		failure{
			echo 'buid fail'
		}
	}
}

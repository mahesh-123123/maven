pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                git branch: 'war', url: 'https://github.com/mahesh-123123/maven.git'
            }
        }
		stage('Build') {
            steps {
                bat 'mvn clean'
				bat 'mvn install'
            }
        }
		stage('Deploy') {
            steps {
				deploy adapters: [tomcat9(credentialsId: 'webserver', path: '', url: 'http://localhost:8080/')], contextPath: 'new-deploy-11', war: '**/*.war'
            }
        }
    }
}

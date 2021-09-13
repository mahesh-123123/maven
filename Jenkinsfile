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
                sh 'mvn clean'
		sh 'mvn install'
            }
        }
	    stage('email') {
            steps {
                mail bcc: '', body: '''hi welcome to jenkins email alerts
                thanks
                msr''', cc: '', from: '', replyTo: '', subject: 'jenkins job', to: 'mmssrraju123@gmail.com'
            }
        }
	    stage('Deploy') {
            steps {
				deploy adapters: [tomcat9(credentialsId: 'webserver', path: '', url: 'http://localhost:8090/')], contextPath: 'new-deploy-11', war: '**/*.war'
            }
        }
		
    }
}

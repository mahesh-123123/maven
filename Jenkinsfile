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
		sh 'mvn package'    
            }
        }
	   
	   /* stage('Deploy') {
            steps {
				deploy adapters: [tomcat9(credentialsId: 'webserver', path: '', url: 'http://localhost:8090/')], contextPath: 'new-deploy-14', war: '/.war'
            }
        }
	    stage('email') {
            steps {
                mail bcc: '', body: '''hi welcome to jenkins email alerts. welcome to deploy-14
                thanks
                msr''', cc: '', from: '', replyTo: '', subject: 'jenkins job', to: 'mmssrraju123@gmail.com'
            }
        }*/
	
        stage('slack') {
            steps {
               slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'devops',
		       color: 'good', message: 'github, jenkins, slack',
		       tokenCredentialId: 'slack-demo', username: 'abc-fdf7447'
            }
        }
		
    }
}

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
		
    }
}

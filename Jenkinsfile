pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'Java17'
    }

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/omiblogger/om.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh '''
                cp target/*.war /opt/tomcat/webapps/
                '''
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }

        stage('Compile and Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }

        stage('Deploy to Tomcat Server') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'TomCatID', path: '', url: 'http://3.250.1.198:8080')], contextPath: 'app', war: '**/*.war'
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp mvn test'
            }
        }

        stage('Compile Build ') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }

        stage('Deploy to Tomat Server') {
            steps {
                deploy adapters:[tomcat9(credentialsId: 'ktomcatID', path: '', url: 'http://3.137.161.198:8080')], contextPath: 'app', war: '**/*.war'
            }
        }

    }
}


        stage('Deploy to Tomat Server') {
            steps {
                deploy adapters:[tomcat9(credentialsId: 'ktomcatID', path: '', url: 'http://3.137.161.198:8080')], contextPath: 'app', war: '**/*.war'
            }
        }

    }
}

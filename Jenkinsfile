pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                // Navigate into SampleWebApp before running mvn test
                sh 'cd SampleWebApp && mvn test'
            }
        }

        stage('Compile Build') {
            steps {
                // Navigate into SampleWebApp and then run the Maven clean package
                sh 'cd SampleWebApp && mvn clean package'
            }
        }

        stage('Deploy to Tomcat Server') {  // Corrected spelling
            steps {
                // Deploy to Tomcat using credentialsId and correct contextPath
                deploy adapters: [tomcat9(credentialsId: 'TomCatID', path: '', url: 'http://3.250.1.198:8080/')], 
                        contextPath: 'app', 
                        war: '**/*.war'
            }
        }
    }
}

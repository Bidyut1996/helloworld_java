pipeline {
    agent any
    
    tools {
        maven 'M399'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Maven Version') {
            
            steps {
                sh '''
                    mvn --version
                 '''
            }
        }
        stage('Checkout') {
            steps {
                script {
                    git branch:'main', url:'https://github.com/Bidyut1996/helloworld_java.git'
                }
            }
        }
        stage('Build') {
            steps {
                sh '''
                    mvn clean package
                '''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                java -jar target/hello-world-1.0-SNAPSHOT.jar
                '''
            }
        }
    }
}

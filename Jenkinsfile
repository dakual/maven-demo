pipeline {
    agent any
    stages {
        stage("Clone repo") {
            steps {
                git 'https://github.com/dakual/maven-demo.git'
            }
        }

        stage("Compile") {
            steps {
                sh 'mvn compile'
            }
        }

        stage("Test") {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }

        stage("Package") {
            steps {
                sh 'mvn clean package'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
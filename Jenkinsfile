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
        }

        stage("Package") {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
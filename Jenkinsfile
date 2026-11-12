pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK25'
    }

    stages {

        stage('Checkout') {
    steps {
        git branch: 'main', url: 'https://github.com/nimitha120706/demo-appMaven.git',
            credentialsId:'Github-Token'

        echo 'Source code downloaded successfully'
    }
}

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }

        stage('Run Application') {
            steps {
                bat 'mvn exec:java -Dexec.mainClass="com.example.app.App"'
            }
        }
    }
}

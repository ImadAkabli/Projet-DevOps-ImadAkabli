pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ImadAkabli/Projet-DevOps-ImadAkabli.git'
            }
        }

        stage('Build & Test') {
            steps {
                dir('bonjour-devops') {
                    sh 'mvn clean test'
                }
            }
        }

        stage('Archive') {
            steps {
                dir('bonjour-devops') {
                    sh 'mvn -DskipTests package'
                    archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
                }
            }
        }
    }
}

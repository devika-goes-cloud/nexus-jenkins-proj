pipeline {
    agent any
    tools {
        jdk 'JAVA_HOME'
        maven 'MAVEN_HOME'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/devika-goes-cloud/secretsanta-gifts-generator.git'
            }
        }
        stage('Build') {
            steps {
                sh "mvn clean package -DskipTests=true"
            }
        }
        stage('nexus push') {
            steps {
                configFileProvider([configFile(fileId: 'settings-id', variable: 'settingsfile')]) {
                    sh "mvn deploy -s $settingsfile"
                }
            }
        }
    }
    post {
        success {
            echo "✅ Build & Deploy successful!"
        }
        failure {
            echo "❌ Build failed. Check logs."
        }
    }
}



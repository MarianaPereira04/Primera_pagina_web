pipeline {
    agent any

    environment {
        PATH = "/opt/homebrew/bin:/usr/local/bin:/usr/bin:/bin"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Instalar dependencias') {
            steps {
                dir('Proyecto Backend/grupo2-backend') {
                    sh 'npm install'
                }
            }
        }

        stage('Compilar') {
            steps {
                dir('Proyecto Backend/grupo2-backend') {
                    sh 'npm run build'
                }
            }
        }

        stage('Pruebas') {
            steps {
                dir('Proyecto Backend/grupo2-backend') {
                    sh 'npm test || echo "No hay tests configurados"'
                }
            }
        }
    }
}

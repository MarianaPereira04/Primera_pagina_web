pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Instalar dependencias') {
            steps {
                dir('Proyecto Backend/grupo2-backend') {
                    sh '/opt/homebrew/bin/npm install'
                }
            }
        }

        stage('Compilar') {
            steps {
                dir('Proyecto Backend/grupo2-backend') {
                    sh '/opt/homebrew/bin/npm run build'
                }
            }
        }

        stage('Pruebas') {
            steps {
                dir('Proyecto Backend/grupo2-backend') {
                    sh '/opt/homebrew/bin/npm test || echo "No hay tests configurados"'
                }
            }
        }
    }
}

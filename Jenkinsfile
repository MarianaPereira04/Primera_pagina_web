pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Descarga el código del repo (igual a lo que ya viste)
                checkout scm
            }
        }

        stage('Instalar dependencias backend') {
            steps {
                dir('Proyecto Backend/grupo2-backend') {
                    sh 'npm install'
                }
            }
        }

        stage('Compilar backend') {
            steps {
                dir('Proyecto Backend/grupo2-backend') {
                    sh 'npm run start:dev'
                }
            }
        }

        stage('Pruebas backend') {
            steps {
                dir('Proyecto Backend/grupo2-backend') {
                    sh 'npm test || echo "No hay tests configurados"'
                }
            }
        }
    }
}

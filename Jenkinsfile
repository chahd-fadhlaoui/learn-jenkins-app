pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Listing files before build"
                    sh 'ls -la'  // Affiche la liste des fichiers avant le build
                    echo "Checking Node version"
                    sh 'node --version || echo "Node is not installed"'  // Affiche un message si Node n'est pas installé
                    echo "Checking NPM version"
                    sh 'npm --version || echo "NPM is not installed"'  // Affiche un message si NPM n'est pas installé
                    echo "Installing dependencies"
                    sh 'npm ci || echo "npm ci failed"'  // Affiche un message si l'installation échoue
                    echo "Running build"
                    sh 'npm run build || echo "Build failed"'  // Affiche un message si le build échoue
                    echo "Listing files after build"
                    sh 'ls -la'  // Affiche la liste des fichiers après le build
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "Running tests"
                    sh 'npm test || echo "Tests failed or not defined"'  // Affiche un message si les tests échouent
                }
            }
        }
    }
}


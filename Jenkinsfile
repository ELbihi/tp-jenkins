pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello depuis un pipeline déclaratif'
            }
        }

        stage('Infos environnement') {
            steps {
                echo "Nom du noeud Jenkins: ${env.NODE_NAME}"
                echo "Workspace: ${env.WORKSPACE}"
            }
        }
                stage('Installation des dépendances') {
            steps {
                bat 'python -m venv .venv'
                bat '.venv\\Scripts\\python.exe -m pip install -r requirements.txt'
            }
        }

        stage('Exécution des tests') {
            steps {
                bat '.venv\\Scripts\\python.exe -m pytest -q'
            }
        }
    }
}
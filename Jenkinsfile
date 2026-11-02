
pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Cloner le depot') {
            steps {
                git url: 'https://github.com/Famorycollab/TP_Jenkins_Git.git',
                    branch: 'main'
            }
        }

        stage('Etape 1 : Verification du depot') {
            steps {
                bat 'echo === Verification du depot ==='
                bat 'git status'
            }
        }

        stage('Etape 2 : Afficher le contenu du projet') {
            steps {
                bat 'echo === Contenu du projet ==='
                bat 'dir'
            }
        }

        stage('Etape 3 : Simuler un deploiement local') {
            steps {
                bat 'echo === Simulation du deploiement ==='
                bat 'echo Le fichier index.html est pret a etre affiche'
            }
        }

        stage('Etape 4 : Fin du build') {
            steps {
                bat 'echo === Fin du build ==='
                bat 'echo SUCCESS'
            }
        }

        stage('Archivage des fichiers') {
            steps {
                archiveArtifacts artifacts: 'index.html, style.css',
                                 fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Build OK'
        }
        failure {
            echo 'Build KO'
        }
    }
}

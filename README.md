pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/LidorDayan/Tes.git', branch: 'main'
            }
        }
        stage('Verify Clone') {
            steps {
                script {
                    if (fileExists('b.py')) {
                        println 'Git repository successfully cloned.'
                    } else {
                        error 'Git repository cloning failed.'
                    }
                }
            }
        }
        stage('Hello') {
            steps {
                script {
                    println 'Hello World'
                }
            }
        }
    }
}

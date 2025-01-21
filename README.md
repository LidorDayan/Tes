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
                    if (fileExists('Bash')) {
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
                stage('Run Python Script') {
            steps {
                script {
                    // Make sure the Python script exists in the repository
                    if (fileExists('script.py')) {
                        sh 'python3 script.py' // Use python or python3 depending on your system
                    } else {
                        error 'Python script not found!'
                    }
                }
            }
        }
    }
}

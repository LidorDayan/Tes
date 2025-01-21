pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Replace 'https://github.com/LidorDayan/Tes.git' with the actual repository URL
                git url: 'https://github.com/LidorDayan/Tes.git', branch: 'main'
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

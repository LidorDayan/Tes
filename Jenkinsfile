pipeline {
    agent any
    parameters {
        string(name: 'CUSTOM_MESSAGE', defaultValue: 'Hello, Jenkins!', description: 'Custom message to echo')
        string(name: 'GIT_REPO_URL', defaultValue: 'https://github.com/LidorDayan/Tes.git', description: 'Git repository URL to clone')
    }
    stages {
        stage('Echo Custom Message') {
            steps {
                script {
                    echo "User's custom message: ${params.CUSTOM_MESSAGE}"
                }
            }
        }
        stage('Clone Repository') {
            steps {
                script {
                 ls
                    }
                }
            }
        }
    }
}

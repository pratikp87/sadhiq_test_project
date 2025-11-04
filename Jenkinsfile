pipeline {
    agent any
  
    environment {
        DEPLOY_USER = 'ubuntu'
        DEPLOY_HOST = '44.223.35.239'
        DEPLOY_PATH = '/var/www/html'
        REPO_URL = 'https://github.com/pratikp87/sadhiq_test_project.git'
        BRANCH = 'main'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: "${REPO_URL}", branch: "${BRANCH}"
            }
        }

        }

        stage('Deploy to Web Server') {
            steps {
                sshagent(['aws-deploy-key']) {
                    sh """
                        scp -o StrictHostKeyChecking=no -r * ${DEPLOY_USER}@${DEPLOY_HOST}:${DEPLOY_PATH}
                    """
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}

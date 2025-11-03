pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/pratikp87/sadhiq_test_project.git', branch: 'main'
            }
        }

        stage('Deploy') {
            steps {
                sshagent(['test']) {
                    sh 'scp -o StrictHostKeyChecking=no readme.md ubuntu@98.94.87.4:/var/www/html/'
                }
            }
        }
    }
}

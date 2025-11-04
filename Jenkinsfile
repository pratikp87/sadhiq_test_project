pipeline {
    agent any
    stages { 
        stage ('checkout') {
            steps {
                git url: 'https://github.com/pratikp87/sadhiq_test_project.git'
            }
        }
        stage ('build') {
             steps { 
                 npm install and npm run build 
             }
        }
    }
} 

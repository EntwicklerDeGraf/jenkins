pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'npm --version'
                sh '''
                    ls -lha
                    echo 'Jenkins test multiple steps'
                '''
            }
        }
    }
}

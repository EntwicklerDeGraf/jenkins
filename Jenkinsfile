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
        stage('deploy') {
            steps {
                sh "echo 'This is a deployment step'"
                sh 'chown jenkins:jenkins simpleScript.sh'
                retry(3) {
                    sh './simpleScript.sh'
                }
                timeout(time: 10, unit: 'SECONDS') {
                    sh 'echo "Waiting for 10 seconds"'
                }
            }
        }
    }
}

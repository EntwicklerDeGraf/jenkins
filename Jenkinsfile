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
                sh 'chmod +x simpleScript.sh'
                retry(3) {
                    sh 'echo "it is repeated several times"'
                    sh './simpleScript.sh'
                }
                timeout(time: 10, unit: 'SECONDS') {
                    sh 'echo "Waiting for 10 seconds"'
                }
                
            }
        }
    }
    post {
        always {
            echo 'The Pipline is finished...'
        }
        success {
            echo '  successfully'
        }
        failure {
            echo '  with errors'
        }
    }
}

pipeline {
    agent any

    stages {
      stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build') {
            steps {
                echo 'make\n'
            }
        }

        stage('Test') {
            steps {
                currentBuild.result = 'FAILURE'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy\n'
            }
        }
    }

    post {
        always {
            script {
                if (currentBuild.result == 'FAILURE') {
                    echo 'pipeline failed'
                }
            }
        }
    }
}

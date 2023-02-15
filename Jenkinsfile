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
                g++ -o my_program my_program.cpp
            }
        }

        stage('Test') {
            steps {
                #!/bin/bash
                ./my_program > output.txt
                cat output.txt
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

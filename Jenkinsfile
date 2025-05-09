pipeline {
    agent {
        node {
            label 'docker-agent-alphine'  // Can be any label with shell support
        }
    }

    triggers {
        pollSCM('* * * * *')  // Every minute
    }

    environment {
        APP_DIR = 'scripts'
    }

    stages {
        stage('Run') {
            steps {
                echo "=== Run Stage ==="
                dir("${APP_DIR}") {
                    sh './hello.sh'
                }
            }
        }
        stage('Build') {
            steps {
                echo "=== Build Stage ==="
                dir("${APP_DIR}") {
                    sh './build.sh'
                }
            }
        }

        stage('Test') {
            steps {
                echo "=== Test Stage ==="
                dir("${APP_DIR}") {
                    sh './test.sh'
                }
            }
        }

        stage('Deliver') {
            steps {
                echo "=== Deliver Stage ==="
                dir("${APP_DIR}") {
                    sh './deliver.sh'
                }
            }
        }
    }
}

pipeline {
    agent docker-agent-alphine

    stages {
        stage('Run Shell Script') {
            steps {
                sh 'scripts/hello.sh'
            }
        }
    }
}

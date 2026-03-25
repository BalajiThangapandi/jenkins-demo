pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh './build.sh > output.txt'
                sh 'cat output.txt'
            }
        }
    }

    post {
        always {
            emailext(
                to: 'your-email@gmail.com',
                subject: "Build Success",
                body: "Build completed successfully. Check attachment.",
                attachmentsPattern: 'output.txt'
            )
        }
    }
}

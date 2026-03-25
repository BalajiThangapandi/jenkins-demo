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
                to: 'balajiharish2000@gmail.com',
                subject: "Jenkins Build: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: "Build completed. Please find the output attached.",
                attachmentsPattern: 'output.txt'
            )
        }
    }
}

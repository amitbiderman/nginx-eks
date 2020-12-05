pipeline {
    agent any
    environment{
        PATH = "$PATH:/home/ec2-user/.local/bin:/home/ec2-user/bin"
    }
    stages{
        stage('Deploy to eks') {
            steps {
                sh "echo Start test"
                sh "echo Finished test"
            }
        }
    }
}

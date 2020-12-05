pipeline {
    agent any
    enviornment{
        PATH = "$PATH:/home/ec2-user/.local/bin:/home/ec2-user/bin"
    }
    stages{
        stage('Deploy to eks') {
            steps{
                script{
                    try{
                        sh "kubectl apply -f /home/ec2-user/nginx-eks/nginx-deployment.yaml"
                    }catch(error){
                        sh "kubectl create -f /home/ec2-user/nginx-eks/nginx-deployment.yaml"
                    }
                }
                sh "kubectl get pods -l 'app=nginx' -o wide | awk {'print \$1\" \" \$3 \" \" \$6'} | column -t"
            }
        }
    }
}

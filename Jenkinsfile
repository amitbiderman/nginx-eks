pipeline {
    agent any
    environment{
        PATH = "$PATH:/home/ec2-user/.local/bin:/home/ec2-user/bin"
    }
    stages{
        stage('Deploy to eks') {
            steps {
                sh "/home/ec2-user/bin/kubectl apply -f nginx-deployment.yaml"
                // script{
                //     try{
                //         sh "sudo /home/ec2-user/bin/kubectl apply -f /home/ec2-user/nginx-eks/nginx-deployment.yaml"
                //     }catch(error){
                //         sh "/home/ec2-user/bin/kubectl create -f /home/ec2-user/nginx-eks/nginx-deployment.yaml"
                //     }
                // }
                sh "/home/ec2-user/bin/kubectl get pods -l 'app=nginx' -o wide | awk {'print \$1\" \" \$3 \" \" \$6'} | column -t"
            }
        }
    }
}

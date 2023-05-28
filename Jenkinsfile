pipeline {
    agent none  
    stages {
 
        stage('Build Environment'){
            agent {
                docker {
                    image 'docker:latest'
                    args '-v /usr/local/bin/kubectl:/usr/local/bin/kubectl -v /var/jenkins_home/kubconfig.yaml:/root/kubconfig.yaml -u root'   
                }
            }
            steps{
               
                   /*sh 'kubectl delete service --all  --kubeconfig=kubconfig.yaml  --kubeconfig=/root/kubconfig.yaml'
                   sh 'kubectl delete pods --all  --kubeconfig=kubconfig.yaml --kubeconfig=/root/kubconfig.yaml'
                   sh 'kubectl delete ingress --all  --kubeconfig=kubconfig.yaml --kubeconfig=/root/kubconfig.yaml'
                   sh 'kubectl delete deployments --all  --kubeconfig=kubconfig.yaml --kubeconfig=/root/kubconfig.yaml'   */                                      
                   sh 'kubectl apply -f traefik.yaml  --kubeconfig=/root/kubconfig.yaml'
                   sh 'kubectl apply -f ingress/  --kubeconfig=/root/kubconfig.yaml'
                   
                  }                   
             }
    }
}

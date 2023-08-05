pipeline {
    agent any
    
    environment {
        //KUBECONFIG = credentials('0062e1c3-3342-44ac-a96f-e9462f88fc1c')
        KUBECONFIG = credentials('871f8298-8a26-4b91-b700-929b7ba0763b')
    }
    
    stages {
        stage('Download ZIP from Nexus') {
            steps {
                script {
                    sh 'curl -o www.zip http://pikukoiptv.zapto.org:8081/repository/filestore/googlebot-front/1.1.2/googlebot-front_02032023_2215.zip'
                }
            }
        }
        
        stage('Unzip') {
            steps {
                script {
                    sh 'rm -rf www'
                    sh 'unzip -j -o www.zip -d www'
                }
            }
        }
        
        stage('Deploy to Kubernetes') {
            steps {
                //kubeconfig(credentialsId: '0062e1c3-3342-44ac-a96f-e9462f88fc1c', serverUrl: 'https://vmi320685.contaboserver.net:6443') {
                    // some block
                    sh "kubectl apply -f deployment.yml"
                //}
            }
        }
    }
}



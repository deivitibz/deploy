pipeline {
    agent any
    
    environment {
        //KUBECONFIG = credentials('0062e1c3-3342-44ac-a96f-e9462f88fc1c')
        KUBECONFIG = credentials('871f8298-8a26-4b91-b700-929b7ba0763b')
        GIT_REPO_URL = 'https://github.com/deivitibz/deploy.git'
        GIT_USER = 'deivitibz'
        GIT_PASSWORD = 'IbizaBonita83'  
    }
    
    stages {
        // stage('Download ZIP from Nexus') {
        //     steps {
        //         script {
        //             sh 'curl -o www.zip http://pikukoiptv.zapto.org:8081/repository/filestore/googlebot-front/1.1.2/googlebot-front_02032023_2215.zip'
        //         }
        //     }
        // }
        
        // stage('Unzip') {
        //     steps {
        //         script {
        //             sh 'rm -rf www'
        //             sh 'unzip -j -o www.zip -d www'
        //         }
        //     }
        // }
        
        // stage('Deploy to Kubernetes') {
        //     steps {
        //         script {
        //             def nginxDeploymentName = 'nginx'
                    
        //             //kubeconfig(credentialsId: '0062e1c3-3342-44ac-a96f-e9462f88fc1c', serverUrl: 'https://vmi320685.contaboserver.net:6443') {
        //             sh "kubectl apply -f deployment.yml"
                    
        //             def podName = sh(script: "kubectl get pods -l app=${nginxDeploymentName} -o jsonpath='{.items[0].metadata.name}'", returnStdout: true).trim()

        //             //sh 'cp -r www ${nginxDeploymentName}:/usr/share/nginx/html'
        //             sh "kubectl cp www/* ${podName}:/usr/share/nginx/html"
        
        //         //}
        //         }
        //     }
        // }

        stage('Make Changes and Commit') {
            steps {
                script {
                    // Navegar al directorio del repositorio
                    dir('nombre_del_repositorio') {
                        // Realizar cambios y crear el commit
                        sh 'echo "Nuevo contenido" >> archivo.txt'
                        sh 'git add archivo.txt'
                        sh 'git commit -m "Mensaje del commit generado por Jenkins"'
                    }
                }
            }
        }
    }
}



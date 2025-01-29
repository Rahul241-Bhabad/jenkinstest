pipeline{
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage("code-deploy"){
            steps{
                sh 'docker pull nginx'
                sh 'docker run -itd --name c-1 -p 80:80 nginx'
            }
        }
    }
}

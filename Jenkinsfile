node{

    stage('SCM Checkout')
    {
        git url: 'https://github.com/arshiyashafiulla/PhpMysql_docker'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'docker-compose build'
        sh 'docker-compose up -d'
    }
    stage('PUSH image to Docker Hub')
    {
        withCredentials([string(credentialsId: 'DockerHubPassword', variable: 'DHPWD')]) 
        {
            sh "docker login -u arshiyanoorain -p ${DHPWD}"
        }
        sh 'docker push arshiyashafiulla/PhpMysql_docker'
    }
}

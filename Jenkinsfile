properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: ''))])
node{
    stage('Scm Checkout sebp/elk')
    {
       git 'https://github.com/spujadas/elk-docker.git'
    }
    stage('Run Elk Stack compose'){
        withCredentials([string(credentialsId: 'docker-login', variable: 'dockerlogin')]) {
        sh "docker login -u ankurgarg21 -p ${dockerlogin}" }
        sh 'docker-compose up -d elk' 
    }
        
}

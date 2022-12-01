pipeline{
    agent{node "ubuntu"}
    stages{
        stage('vcs'){
            step{
                git branch:"main",
                     url: "https://github.com/saisatyateja/docker.git"
            }
        }
        stage('execute'){
            step{
                sh "sh dockerinfo.sh"
            }
        }
    }
}
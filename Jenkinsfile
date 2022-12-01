pipeline{
    agent{node "ubuntu"}
    stages{
        stage('vcs'){
            steps{
                git branch:"main",
                     url: "https://github.com/saisatyateja/docker.git"
            }
        }
        stage('execute'){
            steps{
                sh "sh dockinfo.sh"
            }
        }
    }
}
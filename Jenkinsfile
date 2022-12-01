pipeline{
   parameters { choice(name: 'choose a node', choices: ['ubuntu', 'centos', 'redhat'], description: 'on what node should i have to run it') }
    agent(node ${params.choose a node})
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
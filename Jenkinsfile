pipeline{
   parameters { choice(name: 'choose_a_node', choices: ['ubuntu', 'centos', 'redhat'], description: 'on what node should i have to run it') }
     
    stages{
     agent(label ${params.choose_a_node})  
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
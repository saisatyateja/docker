/*pipeline{
   parameters { choice(name: 'choose_a_node', choices: ['ubuntu', 'centos', 'redhat'], description: 'on what node should i have to run it') }
     agent { label "${params.choose_a_node}" }
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
}*/

pipeline{
    agent{
        label "node1"
    }
    stages{
        stage("vcs"){
            steps{
                git url:"https://github.com/DevProjectsForDevOps/StudentCoursesRestAPI.git" ,
                    branch:"master"
                 
            }
        }
        stage("image build"){
            steps{
               sh 'docker image build -t studentcourserestapi:1.0 .'
               sh 'docker tag studentcourserestapi:1.0 saisatyateja/studentcourserestapi:1.0'
            }        
        }
        stage("docker hub push"){
            steps{
               sh 'docker push saisatyateja/studentcourserestapi:1.0'

            }
        }
        stage("start container"){
            steps{
                sh 'docker container run -d -p 8083:8080 --name "stdcourse" studentcourserestapi:1.0'
            }
        }
    }
}
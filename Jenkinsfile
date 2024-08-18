pipeline{
    agent {
        node{
            label 'JenkinsSlaveNodeLabel'
        }
    }
    stages{
        stage("checkout code stage"){
            steps{
                git url: 'https://github.com/Subham12345srk/day2jenkinsrepo.git',branch:'main'           
                 }
        }
        stage("Cleanup Stage"){
            steps{
                sh 'docker rm -f $(docker ps -aq)'
                sh 'docker rmi -f myimage'
            }
        }
                                
        stage("Build docker image"){
            steps{
                sh 'docker build -t myimage .'

            }
        }
        stage("Create Container"){
            steps{
                sh 'docker run -d -p 8501:8501 myimage'

            }
        }
        }
    }

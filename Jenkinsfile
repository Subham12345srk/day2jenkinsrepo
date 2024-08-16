pipeline{
    agent any
    stages{
        stage("checkout code stage"){
            steps{
                git url: 'https://github.com/Subham12345srk/day2jenkinsrepo.git',branch:'main'           
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

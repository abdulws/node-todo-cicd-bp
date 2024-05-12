@Library("Shared_lib@main") _

pipeline {
    agent any
    
    stages {
        stage("Clean Workspace"){
            steps{
                script{
                    cleanWs()
                }
            }
        }
        
        stage("Code checkout"){
            steps{
                script{
                    git url: "https://github.com/DevMadhup/node-todo-cicd.git", branch: "master"
                }
            }
        }
        
        stage("Build Docker image"){
            steps{
                script{
                        docker_build("node-app","latest","madhupdevops")  
                }
            }
        }

        stage("Push Docker image"){
            steps{
                script{
                        docker_push("node-app","latest","madhupdevops")  
                }
            }
        }
    }
}

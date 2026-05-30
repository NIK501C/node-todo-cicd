@Library("Shared") _
pipeline {
    agent {label "vinod"}
    stages{
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Clone Code"){
            steps{
                script{
                    clone("https://github.com/NIK501C/node-todo-cicd.git","master")
                }
            }
        }
        stage("Build"){
           steps{
                script{
                    build("node-groovy")
                }
           }
        }
        stage("Push"){
            steps{
                script{
                    push("node-groovy")
                }
            }
        }
        stage("Test"){
            steps{
                echo "This stage is testing"
                sh "sudo docker run -d -p 8000:8000 node-groovy:latest"
            }
        }
        stage("Deploy"){
            steps{
                echo "This stage is deploying"
                echo "Finished Jenkinsfile"
            }
        }
    }
}

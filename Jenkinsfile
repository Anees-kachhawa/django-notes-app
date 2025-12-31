@Library('Shared')_
pipeline{
    agent { label 'phew'}
    
    stages{
        stage("Clone"){
            steps{
                script{
                clone("https://github.com/LondheShubham153/django-notes-app.git","main")
                }
            }
        }
        stage("Clean Workspace"){
            steps{
                sh 'sudo rm -rf data/mysql || true'
            }
        }
        stage("Code Building"){
            steps{
                script{
                    docker_build("notes-app","latest","anishhhhhh")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("notes-app","latest","anishhhhhh")
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "Do something man"
                sh "docker compose down && docker compose up -d"
                echo "Lets's see if poll SCM is working or not"
            }
        }
    }
}

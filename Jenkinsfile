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
        stage("Code Build"){
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
                echo "This is the SCM from github latest"
                deploy()
            }
        }
    }
}

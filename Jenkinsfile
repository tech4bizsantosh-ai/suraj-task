pipline {
    agent any
    environment {
        IMAGES-NAME = "devpos-task"

        CONTAINER-NAME = "devops-task-container"
    }

    stages {
        stage ("clone git repo") {
            steps {
                sh 'git https://github.com/tech4bizsantosh-ai/suraj-task.git'
            }
        }

        stage ("Docker images build"){
            steps {
                sh 'docker build -t $IMAGES-NAME .'

            }
        }

        stage ("run docker container") {
            stage {
                sh ' docker run -d -p 80:8080 --name $CONTAINER-NAME devops-task:latest'
            }
        }

    }

    

}

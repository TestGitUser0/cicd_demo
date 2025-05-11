Pipeline{
    agent{
        label "master"
    }

    stages{
        stage("Clean up"){
            steps{
                deleteDir()
            }
        }
        stage("Clone repo"){
            steps{
                sh 'git clone URL'
            }
        }
        stage("Build"){
            step{
                sh 'docker build -t nginx:latest .'
                sh 'docker container run --name nginx -d -p 8080:80 '
            }
        }
    }

}
pipeline{
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
                sh 'git clone https://github.com/TestGitUser0/cicd_demo.git'
            }
        }
        stage("Build"){
            steps{
                dir('cicd_demo'){
                    sh 'docker build -t nginx:latest .'
                    sh 'docker container run -d -p 8080:80 nginx'
                }
            }
        }
    }

}
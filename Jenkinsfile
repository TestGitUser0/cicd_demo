pipeline{
    agent{
        label "secondVM"
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
                    script{
                        sh 'docker container ls'
                        if (env.BRANCH_NAME == 'main') {
                            echo "本番環境にデプロイ"
                            sh  '''
                            docker build -t nginx-prod .
                            docker container run -d -p 8080:80 nginx-prod
                            '''
                        }
                        else {
                            echo "開発環境にデプロイ"
                            sh '''
                            docker build -t nginx-dev .
                            docker container run -d -p 8081:80 nginx-dev
                            '''
                        }
                    }
                }
            }
        }
    }
}
pipeline{
    agent {label 'worker'}
    stages{
        stage("Build"){
            steps{
                sh "cd vote"
                sh "aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 584716546011.dkr.ecr.ap-south-1.amazonaws.com"
                sh "docker build -t 584716546011.dkr.ecr.ap-south-1.amazonaws.com/democ51:v${BUILD_NUMBER} ."
                sh "docker push 584716546011.dkr.ecr.ap-south-1.amazonaws.com/democ51:v${BUILD_NUMBER}"
            }
        }
        stage("Deploy"){
            steps{
                sh "echo deploy"
            }
        }
    }
}

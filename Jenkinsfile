pipeline{
    agent {label 'worker'}
    stages{
       stage("Build and Push"){
        steps{
            sh '''
            cd vote
            docker build -t dipesh017/vote:v2 .
            '''
        }
       } 
       stage("Deploy"){
        steps{
            sh "echo docker run"
        }

       }
    }
}

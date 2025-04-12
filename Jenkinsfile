pipeline{
    agent {label 'worker'}
    options {
        buildDiscarder(logRotator(numToKeepStr: '15'))
        disableConcurrentBuilds()
        retry(2)
        timeout(time: 15, unit: 'MINUTES')
    }
    stages{
       stage("Build and Push"){
        steps{
            sh "cd vote"
            sh "docker build -t dipesh017/vote:v1"
        }
       } 
       stage("Deploy"){
        steps{
            sh "echo docker run"
        }

       }
    }
}

pipeline {
    agent {
        label 'worker'
    }
    options{
        buildDiscarder(logRotator(numToKeepStr: '15'))
        disableConcurrentBuilds()
        retry(2)
        timeout(time: 5, unit: 'MINUTES')
    }
    parameters {
        string(name: 'BRANCH', defaultValue: 'develop', description: 'Enter the branch')
    }
    stages{
        stage("Docker Build and Push"){
            steps{
                sh '''
                cd vote
                aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 584716546011.dkr.ecr.ap-south-1.amazonaws.com
                docker build -t 584716546011.dkr.ecr.ap-south-1.amazonaws.com/vote:v${BUILD_NUMBER}
                docker push 584716546011.dkr.ecr.ap-south-1.amazonaws.com/vote:v${BUILD_NUMBER}
                '''
            }

        }
        stage("Deploy"){
            parallel{
                stage("Dev Deployment"){
                    steps{
                        sh "echo actual steps"
                        sh "sleep 30"
                    }
                }
                stage("QA Deployment"){
                    steps{
                        sh "echo actual steps"
                        sh "sleep 30"
                    }
                }               
            }
        }

    }
}

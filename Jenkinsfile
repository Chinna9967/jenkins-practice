pipeline{
    agent { node { label 'agent1'} }

    stages{
        stage('Build'){
            steps{
                echo 'Building'
            }
        }
        stage('Test'){
            steps{
                echo 'testing'
            }    
        }
        stage('Deploy'){
            steps{
                echo 'Deploying.....'
            }
        }
    }
    post{
        always{
            echo 'iam always running whether job is sucess or not'
        }
        sucess{
            echo 'iam running when job is success'
        }
        failure{
            echo 'iam running when the job is failure'
        }
    }
}
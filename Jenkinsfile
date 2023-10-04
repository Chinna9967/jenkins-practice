pipeline{
    agent { node { label 'agent1'} }

    stages{
        stage('Build'){
            steps{
                echo 'Building'
                sh 'ls -ltr'
                sh 'pwd'
                sh '''
                 ls -ltr
                 pwd
                 echo 'hello shell'
                '''
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
                // error 'this is failed'
            }
        }
    }
    post{
        always{
            echo 'iam always running whether job is sucess or not'
        }
        success{
            echo 'iam running when job is success'
        }
        failure{
            echo 'iam running when the job is failure'
        }
    }
}
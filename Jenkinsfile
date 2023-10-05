pipeline{
    agent { node { label 'AGENT-1'} }
    options{
        timeout(time: 1,unit: 'HOURS')
        // ansiColor('xterm')
    }
    environment{
        USER= 'kashi'
    }
    stages{
        stage('Build'){
            steps{
                echo 'Building'
                sh 'ls -ltr'
                sh 'pwd'
                sh '''
                 ls -ltr
                 pwd
                 echo 'hello shell to test webhook'
                 printenv
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
        stage('Example'){
            environment{
                AUTH = credentials('ssh-auth')
            }
            steps{
                sh 'printenv'
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
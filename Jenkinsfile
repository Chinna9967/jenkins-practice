pipeline{
    agent { node { label 'AGENT-1'} }
    options{
        timeout(time: 1,unit: 'HOURS')
        // ansiColor('xterm')
    }
    environment{
        USER= 'kashi'
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage('params'){
            Steps{
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
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
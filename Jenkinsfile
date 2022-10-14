pipeline {
    agent any
    environment{
        name='piyush'
    }
    parameters{
        string(name:'person',defaultValue:'piyush kumar',description: "whoa are you?")
        booleanParam(name: 'isMale', defaultValue:true, description:"")
        choice(name: 'City', choices: ['jaipur','Nainital','agra','alwar'], description: "")
    }
    stages {
        stage('Run a command') {
            steps {
                sh '''
                ls
                date
                pwd
                '''
            }
        }
        stage('Parameters') {
            environment{
                username='myusername'
            }
            steps {
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        stage('Continue ?') {
            input {
                message "Should we continue?"
                ok "yes we should"
            }
            steps {
                echo 'This stage is continue'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Deploy on prod'
            }
        }
    }
    post {
        always{
            echo "i will always say hello again "
        }
        failure {
            echo "failure"
        }
        success {
            echo "success"
        }
    }
}

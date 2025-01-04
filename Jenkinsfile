pipeline {
    agent any
    environment {
        name = 'Juhi'
    }
    parameters {
        string(name: 'Person', defaultValue: 'Ayush Singh', description: "Who are you?")
        booleanParam(name: 'isMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Patna', 'Mumbai', 'Bangalore'], description: "")

    }
    stages {
        stage('Run a command') {
            steps {
                sh '''
                ls 
                date
                pwd
                cal 2025
                '''
            }
        }
        stage('Environment Variables') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'

            }
        }
        stage('Parameters') {
            steps {
                echo 'Deploy on test'
                sh 'echo "${name}"'
                sh 'echo "${Person}"'
            }
        }
        stage('Continue') {
            input{
                message "Should we continue?"
                ok "yes we should"
            }
            
            steps {
                echo 'Deploy on Prod'
            }
        }
        stage('Deploy on Prod') {
            steps {
                echo 'Deploy on Prod'
            }
        }
    }
        post{
            always {
                echo 'I will always say hello again!'
            }
            failure{
                echo 'failure'
            }
            success{
                echo 'Success'
            }
        }
    }

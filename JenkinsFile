pipeline {
    agent any
    environment {
        name = 'firdoush'
    }
    parameters {
        string(name: 'person', defaultValue: 'firdoush', description: "who are you?")
        booleanParam(name: 'isMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Jaipur','Mumbai','Pune'], description: "")
    }
    
    stages {
        stage('Run a command') {
            environment {
                usern = 'Harsh'
            }
            steps {
                sh '''
                ls
                pwd
                hostname -i
                echo "$usern"
                '''
            }
        }
        
        stage('Enviroment variable') {
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}"'
                sh 'echo "${usern}"'
            }
        }
        
        stage('Continue ?') {
            input {
                message "should we continue?"
                ok "Yes we should."
            }
            steps {
                echo 'Deploy to prod'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        
        stage('Parameters') {
            steps {
                echo 'Deploy to prod'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
    }
    
    post {
        always {
            echo 'i will execute always'
        }
        failure {
            echo 'Failure'
        }
        success {
            echo 'success'
        }
    }
}

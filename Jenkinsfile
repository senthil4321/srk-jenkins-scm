pipeline {
    agent any
        parameters {
        choice(
            choices: ['greeting' , 'silence'],
            description: '',
            name: 'REQUESTED_ACTION')
    }
    stages {
        stage('Stage 1') {
            steps {
                echo 'Hello world!'
            }
        }

         stage('Stage 2') {
            steps {
                echo 'Hello world2!'
            }
        }
    }
}

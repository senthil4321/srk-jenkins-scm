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
        stage ('Speak') {
            when {
                // Only say hello if a "greeting" is requested
                expression { params.REQUESTED_ACTION == 'greeting' }
            }
            steps {
                echo "Hello, greeting!"
            }
        }
    }
}

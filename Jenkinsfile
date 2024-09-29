properties([
   parameters([
	activeChoice(
        choiceType: 'PT_SINGLE_SELECT',
        filterLength: 1,
        filterable: false,
        name: 'Env',
        script: groovyScript(
            fallbackScript: [
                classpath: [],
                oldScript: '',
                sandbox: true,
                script: "return ['Could not get the environments']"
            ],
            script: [
                classpath: [],
                oldScript: '',
                sandbox: true,
                script: "return ['TYPE1', 'TYPE2', 'TYPE3', 'TYPE4']"
            ]
        )
          ),
	      [
         $class: 'ChoiceParameter',
         choiceType: 'PT_SINGLE_SELECT',
         description: "Select which type",
         filterLength: 1,
         filterable: false, 
         name: 'TYPE', 
         script: [
            $class: 'GroovyScript', 
            fallbackScript: [
               classpath: [], 
               sandbox: true,
               script: "return['']"
            ], 
            script: [
               classpath: [], 
               sandbox: true,
               script: "return ['TYPE1', 'TYPE2', 'TYPE3', 'TYPE4']"
            ]
         ]
      ],
      [
         $class: 'CascadeChoiceParameter',
         choiceType: 'PT_SINGLE_SELECT', 
         description: 'Select which sub type',
         name: 'SUB_TYPE', 
         referencedParameters: 'TYPE',
         script: [
            $class: 'GroovyScript', 
            fallbackScript: [
               classpath: [], 
               sandbox: true, 
               script: "return['Select which type']"
            ], 
            script: [
               classpath: [], 
               sandbox: true,
               script:  "return['Select which type']"
            ] 
         ]
      ]
   ])
])
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

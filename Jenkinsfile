properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any
    environment{
        COMPONENT = ''
        SOURCE_VERSION = ''
        ARTIFACTORY_USER = ''
    }
    stages {
         stage ('Checkout'){
             steps{
                git credentialsId: 'f3b19650-ee19-4187-9152-e2b4f894e7aa', url: 'https://github.com/cody6750/tester'  
            }      
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Merge') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Promotion') {
          /*  when {
              branch        'master'
              promoteTo     'production'
            }
            steps {
                echo 'Promote to Prod....'
            }*/
           /* when {
                branch      'master'
                promoteTo   'stage'
            }*/
            steps {
                echo 'Promote to Stage....'
            }
        }
    }
}

pipeline {
    properties([pipelineTriggers([githubPush()])])    
    agent any
    environment{
        COMPONENT = ''
        SOURCE_VERSION = ''
        ARTIFACTORY_USER = ''
    }
    
    stages {
         stage ('Checkout'){
        git branch: 'exampleBranch', url: 'https://github.com/example-org/example-repo.git'
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
            when {
              branch        'master'
              promoteTo     'production'
            }
            steps {
                echo 'Promote to Prod....'
            }
            when {
                branch      'master'
                promoteTo   'stage'
            }
            steps {
                echo 'Promote to Stage....'
            }
        }
    }
}
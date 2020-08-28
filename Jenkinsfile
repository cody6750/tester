pipeline {
    agent any
    environment{
        COMPONENT = ''
        SOURCE_VERSION = ''
        ARTIFACTORY_USER = ''
        ARTIFACTORY_PASSWORD = $(aws --region us-east-1 ssm get-parameter --name "/cicd/jfrog/platform/user/${ARTIFACTORY_USER}/password" --with-decryption --query 'Parameter.Value' --output text)
}
    stages {
        stage ('SCM Checkout') {
            git 'https://github.com/Tealium/java-platform'
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
properties([pipelineTriggers([githubPush()])])

node {
    stage ('Checkout'){
        git credentialsId: 'f3b19650-ee19-4187-9152-e2b4f894e7aa', url: 'https://github.com/cody6750/tester'        
    }
    stage ('Build'){
        steps{
            echo 'Testing..'

        }
    }
    stage ('Test'){
        steps{
            echo 'Testing..'
        }
    }
}  
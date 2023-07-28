
def semanticVersion = "${env.BUILD_NUMBER}.0.0"
def packageName = "devops_pipeline_demo_${env.BUILD_NUMBER}"
def version = "${env.BUILD_NUMBER}.0"


pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build Step -- Testing1 '
            }
        }
        stage('Test') {
            steps {
                echo "Test Step  -- Testing2  pipeliname=====  ${env.JOB_NAME}    branchName == ${env.BRANCH_NAME}     env.GIT_BRANCH  == ${env.GIT_BRANCH}"

                    snDevOpsArtifact(artifactsPayload:"""{"artifacts": [
                                {"name": "demo1.jar","version": "${version}","semanticVersion": "${semanticVersion}","repositoryName": "demo1"},
                                {"name": "demo2.jar","version": "${version}","semanticVersion": "${semanticVersion}","repositoryName": "demo2"},
                                {"name": "demo3.jar","version": "${version}","semanticVersion": "${semanticVersion}","repositoryName": "demo3"},
                                {"name": "demo4.jar","version": "${version}","semanticVersion": "${semanticVersion}","repositoryName": "demo4"},
                                {"name": "demo5.jar","version": "${version}","semanticVersion": "${semanticVersion}","repositoryName": "demo5"}]}""")
                                echo "Deploying.."

                
                snDevOpsChange();

            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy Step'
                
            }
        }
    }
}

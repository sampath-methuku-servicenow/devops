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

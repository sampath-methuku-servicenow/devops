pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build Step -- Testing1 '
                echo "  pipeliname=====  ${env.JOB_NAME}    branchName == ${env.BRANCH_NAME}"
                snDevOpsChange();
            }
        }
        stage('Test') {
            steps {
                echo "Test step"
                script {
                   number=snDevOpsGetChangeNumber (changeDetails: """{ "pipeline_name": "github_multi_branch_pipeline/scratch/testing", "build_number": "${env.BUILD_NUMBER}", "stage_name": "Build", "branch_name": "${env.BRANCH_NAME}" }""");                  
                    echo "Change Number =="+number;
                 echo "Chnage nUMBER===="+number
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy Step'
                
            }
        }
    }
}

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
                echo "Test Step  -- Testing2  pipeliname=====  ${env.JOB_NAME}    branchName == ${env.BRANCH_NAME}"
                snDevOpsChange();
                script {
                   number=snDevOpsGetChangeNumber (changeDetails: """{ "pipeline_name": "github_multi_branch_pipeline/release/2023-06--Test2", "build_number": "${env.BUILD_NUMBER}", "stage_name": "Test", "branch_name": "${env.BRANCH_NAME}" }""");                  
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

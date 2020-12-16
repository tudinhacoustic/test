pipeline{

    agent any 

    stages{
        stage("A"){
            steps{
                echo "___Tú Đẹp Trai___"
                echo "${GIT_COMMIT}"
                echo "${GIT_COMMITTER_NAME}"
                echo "${GIT_AUTHOR_NAME}"
                echo "${GIT_URL}"
                echo "${GIT_URL_N}"
                echo "${GIT_BRANCH}"
                echo "${GIT_LOCAL_BRANCH}"
                echo "${GIT_PREVIOUS_COMMIT}"
                echo "${GIT_PREVIOUS_SUCCESSFUL_COMMIT}"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
pipeline{

    agent any 

    stages{
        stage("A"){
            steps{
                echo "___Tú Đẹp Trai___"
                echo "${GIT_COMMIT}"
                echo "${BRANCH_NAME}"
                echo "${env}"
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
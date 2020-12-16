pipeline{

    agent any 

    environment {
        TELEGRAM_GROUP = -438532935
        GIT_NAME=$(git --no-pager show -s --format='%an' $GIT_COMMIT)
        GIT_EMAIL=$(git --no-pager show -s --format='%ae' $GIT_COMMIT)
    }

    stages{
        stage("A"){
            steps{
                echo "${GIT_COMMIT}"
                echo "${GIT_NAME}"
                echo "${GIT_EMAIL}"
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
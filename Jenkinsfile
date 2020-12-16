pipeline{

    agent any 

    stages{
        stage("A"){
            steps{
                echo "___Tú Đẹp Trai___"
                echo "Git Commit $GIT_COMMIT"
                echo "Env Git Name ${env.GIT_COMMITTER_NAME}"
                echo "Env Git Author Name ${env.GIT_AUTHOR_NAME}"
                echo "Git Author Name $GIT_AUTHOR_NAME"
                echo "Git Commiter Name $GIT_COMMITTER_NAME"
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
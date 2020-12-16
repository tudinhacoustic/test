pipeline{

    agent any 

    stages{
        stage("A"){
            steps{
                script {
                    env.GIT_COMMIT_MSG = sh (script: 'git log -1 --pretty=%B ${GIT_COMMIT}', returnStdout: true).trim()
                }
                echo "${GIT_COMMIT_MSG}"
                echo GIT_COMMIT %GIT_COMMIT% 
                echo GIT_BRANCH %GIT_BRANCH%
                echo GIT_LOCAL_BRANCH %GIT_LOCAL_BRANCH%
                echo GIT_PREVIOUS_COMMIT %GIT_PREVIOUS_COMMIT%
                echo GIT_PREVIOUS_SUCCESSFUL_COMMIT %GIT_PREVIOUS_SUCCESSFUL_COMMIT%
                echo GIT_URL %GIT_URL%
                echo GIT_URL_N - %GIT_URL_N%
                echo GIT_AUTHOR_NAME %GIT_AUTHOR_NAME%
                echo GIT_COMMITTER_EMAIL %GIT_COMMITTER_EMAIL%
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
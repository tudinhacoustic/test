pipeline{

    agent any 

    environment {
        env.GIT_COMMIT_MSG = sh (script: 'git log -1 --pretty=%B ${GIT_COMMIT}', returnStdout: true).trim()
        env.GIT_COMMITTER_EMAIL = sh(script: "git --no-pager show -s --format='%ae'", returnStdout: true).trim()
        env.GIT_COMMITTER_NAME = sh(script: "git --no-pager show -s --format='%an'", returnStdout: true).trim()
    }

    stages{
        stage("A"){
            steps{
                echo "${env.GIT_COMMIT_MSG}"
                echo "${env.GIT_COMMITTER_EMAIL}"
                echo "${env.GIT_COMMITTER_NAME}"
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
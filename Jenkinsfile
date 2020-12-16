pipeline{

    agent any 

    environment {
        TELEGRAM_GROUP = -438532935
    }

    stages{
        stage("A"){
            steps{
                script {
                    env.GIT_COMMIT_MSG = sh (script: 'git log -1 --pretty=%B ${GIT_COMMIT}', returnStdout: true).trim()
                    env.GIT_COMMITTER_EMAIL = sh(script: "git --no-pager show -s --format='%ae'", returnStdout: true).trim()
                    env.GIT_COMMITTER_NAME = sh(script: "git --no-pager show -s --format='%an'", returnStdout: true).trim()
                }
                telegramSend(message:"Pipeline for branch ${GIT_BRANCH}, project tudinhacoustic/go-api passed. Details: https://github.com/tudinhacoustic/go-api/commit/${GIT_COMMIT}",chatId:"${TELEGRAM_GROUP}")
                echo "${env.GIT_COMMIT_MSG}"
                echo "${env.GIT_COMMITTER_EMAIL}"
                echo "${env.GIT_COMMITTER_NAME}"
                echo "${GIT_BRANCH}"
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
            echo "${env.GIT_COMMIT_MSG}" 
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
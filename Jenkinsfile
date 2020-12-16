pipeline{

    agent any 

    stages{
        stage("A"){
            steps{
                script {
                    env.GIT_COMMIT_MSG = sh (script: 'git log -1 --pretty=%B ${GIT_COMMIT}', returnStdout: true).trim()
                    env.GIT_COMMITTER_EMAIL = sh(script: "git --no-pager show -s --format='%ae'", returnStdout: true).trim()
                    env.GIT_COMMITTER_NAME = sh(script: "git --no-pager show -s --format='%an'", returnStdout: true).trim()
                }
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
        script {
          env.GIT_COMMIT_MSG = sh (script: 'git log -1 --pretty=%B ${GIT_COMMIT}', returnStdout: true).trim()
          env.GIT_COMMITTER_EMAIL = sh(script: "git --no-pager show -s --format='%ae'", returnStdout: true).trim()
          env.GIT_COMMITTER_NAME = sh(script: "git --no-pager show -s --format='%an'", returnStdout: true).trim()
        }
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
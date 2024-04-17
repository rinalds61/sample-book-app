pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script{
                    build()
                }
            }
        }
        stage('Deploy to dev') {
            steps {
                script{
                    deploy("DEV", 1010)
                }
            }
        }
        stage('Test on Dev') {
            steps {
                script{
                    test("DEV")
                }
            }
        }

        stage('Deploy to STG') {
            steps {
                script{
                    deploy("STG", 1020)
                }
            }
        }
        stage('Test on STG') {
            steps {
                script{
                    test("STG")
                }
            }
        }

        stage('Deploy to PRD') {
            steps {
                script{
                    deploy("PRD", 1030)
                }
            }
        }
        stage('Test on PRD') {
            steps {
                script{
                    test("PRD")
                }
            }
        }
    }
}
//for windows : bat "npm ..."
def deploy(String environment, int port){
    echo "Deployment to ${environment} has started"
    bat "pm2 delete ${environment}"
    bat "pm2 start -n \"${environment}\" index.js -- ${port}"
}

def test(String environment){
    echo "Testing on ${environment} has started"
    bat "npm test"
}
def build(){
    echo 'Build started'
    bat "ls"
    bat "npm install"
}
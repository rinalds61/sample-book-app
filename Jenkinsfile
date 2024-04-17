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
                    deploy("DEV")
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
                    deploy("STG")
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
                    deploy("PRD")
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

def deploy(String environment){
    echo "Deployment to ${environment} has started"
}

def test(String environment){
    echo "Testing on ${environment} has started"
}
def build(){
    echo 'Build started'
}
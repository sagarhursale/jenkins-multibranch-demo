pipeline {
    agent any

    stages {

        stage('Show Branch Name') {
            steps {
                echo "=============================="
                echo "Running for branch: ${env.BRANCH_NAME}"
                echo "=============================="
            }
        }

        stage('Build') {
            steps {
                echo "Build started..."
                sleep 3
                echo "Build completed"
            }
        }

        stage('DEV Deployment') {
            when {
                branch 'dev'
            }
            steps {
                echo "Deploying application to DEV environment"
            }
        }

        stage('Approval for PROD') {
            when {
                branch 'prod'
            }
            steps {
                input message: "Approve deployment to PROD?"
            }
        }

        stage('PROD Deployment') {
            when {
                branch 'prod'
            }
            steps {
                echo "Deploying application to PROD environment"
            }
        }
    }
}


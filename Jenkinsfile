pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                echo "Building version $(NEW_VERSION)"
            }
        }
        stage("Push") {
            steps {
                echo 'Pushing Build to ECR'
            }
        }
        stage("Deploy") {
            steps {
                echo 'Deploying to ECS ....'
            }
        }
    }
}

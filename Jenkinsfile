pipeline {
    agent any
    parameters {
        //string(name: 'VERSION', defaultValue: '', description: 'version to deploy on dev')
        //choice(name: 'VERSION', choices: [''1.1.0','1.2.0','1.3.0'], description: 'version to deploy on dev')
        booleanParam(name: 'executePush', defaultValue: true, description: 'test only when ticked')
    }
    stages {
        stage("Build") {
            steps {
                echo 'Building..'
            }
        }
        stage("Push") {
            when {
                expression {
                    params.executePush   
                }    
            }    
            steps {
                echo 'Pushing Build to ECR'
            }
        }
        stage("Deploy") {
            steps {
                echo 'Deploying to ECS ....'
                echo "Deplying version ${params.VERSION}"
            }
        }
    }
}

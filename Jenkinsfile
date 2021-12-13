pipeline {
    agent any
    parameters {
        string(name: 'VERSION', defaultValue: '', description: 'version to deploy on dev')
        choice(name: 'VERSION', choices: [''1.1.0','1.2.0','1.3.0'], description: 'version to deploy on dev')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'test only when ticked')
    }
    stages {
        stage("Build") {
            steps {
                echo 'Building..'
            }
        }
        stage("Test") {
            when {
                expression {
                    params.executeTests   
                }    
            }    
            steps {
                echo 'Testing..'
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

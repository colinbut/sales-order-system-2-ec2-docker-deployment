pipeline {
    // runs on any 'agent' (can either be a master or slave) that has ansible installed
    agent any
    parameters {
        string(name: 'MICROSERVICE_NAME', description: 'The microservice to deploy')
        string(name: 'MICROSERVICE_VERSION', description: 'The version to deploy')
        string(name: 'MICROSERVICE_PORT', description: 'The microservice port')
    }
    stages {
        stage('Execute Ansible Playbook') {
            steps {
                // Needs Ansi Plugin that enables colourful printing on Console Log output
                ansiColor('xterm') {
                    ansiblePlaybook(
                        playbook: "deploy_${params.MICROSERVICE_NAME}.yml", 
                        inventory: 'hosts', 
                        extraVars: [
                                VERSION: "${params.MICROSERVICE_VERSION}", 
                                HOST_PORT: "${params.MICROSERVICE_PORT}", 
                                CONTAINER_PORT: "${params.MICROSERVICE_PORT}", 
                                MICROSERVICE_NAME: "${params.MICROSERVICE_NAME}"
                                ], 
                        installation: 'ansible', 
                        credentialsId: 'ssh-to-server', 
                        disableHostKeyChecking: true,
                        colorized: true, 
                    )
                }
                
            }
        }
    }
}
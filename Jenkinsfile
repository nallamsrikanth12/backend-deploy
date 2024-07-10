pipeline {
    agent {
        label 'Agent-1'
    }
    options {
        // Timeout counter starts BEFORE agent is allocated
        timeout(time: 30, unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters {
        string(name: 'appversion', defaultValue: '1.0.0', description: 'What is my version?')

    }
    environment {
        def appversion = '' // variable declaration
        nexusUrl = 'nexus.srikantheswar.online:8081'
    }

    stages {
        stage ('print the version') {
            steps {
            sh """
                echo "what is y version is ${params.appversion}"
            """

        }
            }
    }
        
    
    post { 
        always { 
            echo 'I will always say Hello again!'
            deleteDir()
        }
        success { 
            echo 'I will run pipeline is success'
        }
        failure { 
            echo 'I will run pipeline is failure'
        }
    }
}

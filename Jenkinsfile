pipeline{
    agent any
    stages{
        stage ('Checkout')
        {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'fe910062-6570-4606-8859-46c10d2815a6', url: 'https://github.com/suraj401/jenkins-docker-example.git']]])
            }
        }
        
        
    }
}

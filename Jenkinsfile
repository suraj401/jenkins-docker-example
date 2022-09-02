pipeline{
    agent any
    stages{
        stage ('Checkout')
        {
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'fe910062-6570-4606-8859-46c10d2815a6', url: 'https://github.com/suraj401/jenkins-docker-example.git']]])
            }
        }
        stage ('Deploy')
        {
            steps{
                sshagent(['main']) {
                   sh "scp -o StrictHostKeyChecking=no -r /var/lib/jenkins/workspace/multiapi_main/* ubuntu@54.167.3.128:/tmp"
                   sh "pwd"
                   sh "ssh ubuntu@54.167.3.128 'cd /tmp && npm install'"
                   sh "ssh ubuntu@54.167.3.128 'cd /tmp && npm build'"
                   sh "ssh ubuntu@54.167.3.128 'cd /tmp && npm run start'"
                    
                   // sh "apt-get install git"
                }
            }
                
            
        }
        
        
    }
}

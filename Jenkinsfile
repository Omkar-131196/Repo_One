pipeline {
    agent {
        label {
            label 'slave-1'
            customWorkspace "/home/ec2-user/jenkins/repo"
        }
    }
    
    stages {
        
        stage ('stage-1') {
            steps {
                sh "yum install httpd -y"
                sh "service httpd start"
            }
        }
        
        stage ('stage-2') {
            steps {
            sh "cp -r /home/ec2-user/jenkins/repo/pipeline/index.html /var/www/html/"
            sh "chmod -R 777 /var/www/html/index.html"
            }
            }
            
        }
        
}

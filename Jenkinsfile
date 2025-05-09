pipeline {
    agent any
    
    stages {
        
        stage ('stage-1') {
            steps {
                sh "yum install httpd -y"
                sh "service httpd start"
            }
        }
        
        stage ('stage-2') {
            steps {
            sh "cp -r /root/.jenkins/workspace/pipeline/index.html /var/www/html/"
            sh "chmod -R 777 /var/www/html/index.html"
            }
            }
            
        }
        
        }
}

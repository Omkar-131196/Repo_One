pipeline {
    agent {
        node {
            label 'slave-1'
            customWorkspace '/home/ec2-user/jenkins/workspace'
        }
    }

    stages {

        stage('stage-1') {
            steps {
                sh "docker system prune -a -f"
                sh "docker run -dp 8001:80 --name 2025Q2 httpd"
                sh "chmod -R 777 /home/ec2-user/jenkins/workspace/index.html"
                sh "docker cp /home/ec2-user/jenkins/workspace/index.html 2025Q2:/usr/local/apache2/htdocs/"
            }
        }
    }
}

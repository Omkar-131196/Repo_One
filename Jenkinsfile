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
                sh "sudo docker system prune -a -f"
                sh "sudo docker volume create httpd_volume"
                sh "sudo cp -r /home/ec2-user/jenkins/workspace/index.html /var/lib/docker/volumes/httpd_volume/_data/"
                sh "sudo chmod -R 777 /var/lib/docker/volumes/httpd_volume/_data/index.html"
            }
        }

        stage('stage-2') {
            steps {
                sh "sudo docker system prune -a -f"
                sh "sudo docker run -dp 80:80 --name 205Q1 httpd"
                sh "sudo docker cp /var/lib/docker/volumes/httpd_volume/_data/index.html 2025Q1:/usr/local/apache2/htdocs/"
            }
        }
    }
}

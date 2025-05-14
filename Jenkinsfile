pipeline {
    agent {
        node {
            label 'master'
        }
    }

    stages {

        stage('stage-1') {
            steps {
                sh "sudo docker system prune -a -f"
                sh "sudo docker volume create httpd_volume"
                sh "sudo cp -r /root/.jenkins/workspace/index.html /var/lib/docker/volumes/httpd_volume/_data/"
                sh "sudo chmod -R 777 /var/lib/docker/volumes/httpd_volume/_data/index.html"
            }
        }

        stage('stage-2') {
            steps {
                sh "sudo docker system prune -a -f"
                sh "sudo docker run -dp 80:80 --name master httpd"
                sh "sudo docker cp /var/lib/docker/volumes/httpd_volume/_data/index.html master:/usr/local/apache2/htdocs/"
            }
        }
    }
}

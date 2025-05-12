pipeline {
    agent {
        node {
            label 'master'
        }
    }

    stages {

        stage('stage-1') {
            steps {
                sh "docker system prune -a -f"
                sh "docker run -dp 80:80 --name master httpd"
                sh "docker cp /root/.jenkins/worskspace/docker/index.html master:/usr/local/apache2/htdocs/"
            }
        }
    }
}

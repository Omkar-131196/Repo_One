pipeline {
    agent {
        node {
            label 'master'
        }
    }

    stages {

        stage('stage-1') {
            steps {
                sh "docker run -dp 90:80 --name 2025Q1 httpd"
                sh "docker cp /root/.jenkins/worskspace/docker/index.html 2025Q1:/usr/local/apache2/htdocs/"
            }
        }
    }
}

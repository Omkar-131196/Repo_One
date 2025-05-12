pipeline {
    agent {
        node {
            label 'master'
        }
    }

    stages {

        stage('stage-1') {
            steps {
                sh "docker run -dp 8001:80 --name 2025Q2 httpd"
                sh "docker cp /root/.jenkins/worskspace/docker/index.html 2025Q2:/usr/local/apache2/htdocs/"
            }
        }
    }
}

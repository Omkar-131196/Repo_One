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
                sh "docker cp /root/.jenkins/worskspace/multi-pipeline_main/index.html master:/usr/local/apache2/htdocs/"
            }
        }
    }
}

pipeline {
    agent {
        node {
            label 'slave-1'
            customWorkspace '/home/ec2-user/jenkins/'
        }
    }

    stages {

        stage('stage-1') {
            steps {
                sh "docker system prune -a -f"
                sh "docker run -dp 90:80 --name 2025Q1 httpd"
                sh "chmod -R 777 /home/ec2-user/jenkins/multi-pipeline_2025Q1/index.html"
                sh "docker cp /home/ec2-user/jenkins/multi-pipeline_2025Q1/index.html 2025Q1:/usr/local/apache2/htdocs/"
            }
        }
    }
}

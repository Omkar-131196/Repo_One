pipeline {
    agent {
        node {
            label 'slave-1'
            customWorkspace '/home/ec2-user/jenkins'
        }
    }

    stages {

        stage('stage-1') {
            steps {
                sh "docker system prune -a -f"
                sh "docker run -dp 80:80 --name master httpd"
                sh "chmod -R 777 /home/ec2-user/jenkins/workspace/multi-pipeline_main/index.html"
                sh "docker cp /home/ec2-user/jenkins/workspace/multi-pipeline_main/index.html master:/usr/local/apache2/htdocs/"
            }
        }
    }
}

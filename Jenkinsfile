pipeline {
    agent {
        node {
            label 'master'
            customWorkspace '/root/repo'
        }
    }

    stages {

        stage('stage-1') {
            steps {
                sh "cd /root"
                sh "mkdir main_branch"
            }
        }
    }
}

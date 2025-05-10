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
                echo "printing in qa branch"
                sh "sudo cd /root"
                sh "sudo mkdir qa_branch"
            }
        }
    }
}

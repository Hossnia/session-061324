pipeline{
    agent {
        label 'ansible-master'
    }
    stages{
        stage("check working directory"){
            steps{
                sh 'pwd'
                sh 'ls'
            }
        }

        stage("delete old artifact if exist"){
            steps{
                sh 'rm -rf *.zip || echo ""'
            }
        }

        stage("create zip file"){
            steps{
                sh 'wget https://github.com/Hossnia/session-061324/archive/refs/heads/main.zip'
            }
        }

        stage("Upload zip file in jfrog"){
            steps{
                sh 'curl -uadmin:AP8gcgmmset5jeYChTJYDN6XmDd \
                -T /home/ec2-user/jenkins/workspace/ansible-playbook/main.zip \
                "http://ec2-100-25-118-58.compute-1.amazonaws.com:8081/artifactory/ansible-playbook/playbooks_${BUILD_ID}.zip"'
            }
        }
    }
}
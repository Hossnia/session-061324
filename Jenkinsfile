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
    }
}
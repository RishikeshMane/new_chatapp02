pipeline {
    agent any

    stages {
        stage('Git  Clone') {
            steps {
                git  'https://github.com/kumar804/new_chatapp.git '
            }
        }

        
        
        stage('Build') {
            steps {
                sh 'rsync -avz -e "ssh -i /var/lib/jenkins/arnav.pem" /var/lib/jenkins/workspace/newchatapp ec2-user@10.0.1.68:~/'
            }
        }
        stage('Deploy') {
            steps {
                sh 'ssh -i /var/lib/jenkins/arnav.pem ec2-user@10.0.1.68 "bash /home/ec2-user/newchatapp/jen.sh"'

            }
        }
    }
}

pipeline {
    agent {
        node {
            label 'awspack2'
        }
    }

    stages {

        stage('terraform started') {
            steps {
                sh 'echo "Started...!" '
            }
        }
        stage('git clone') {
            steps {
                sh 'sudo rm -r *;sudo git clone https://github.com/devops98/terraJenkins.git'
            }
        }
       /* stage('tfsvars create'){
            steps {
                sh 'sudo cp /home/ec2-user/vars.tf ./jenkins/'
            }
        } */
	    
	stage('terraform mkdir') {
            steps {
                sh 'sudo mkdir testdir'
            }
        }
        stage('terraform init') {
            steps {
                sh 'ls;sudo terraform init'
            }
        }
        stage('terraform plan') {
            steps {
                sh 'terraform plan'
            }
        }
		
		stage('terraform apply') {
            steps {
                sh 'terraform apply'
            }
        }
		
        stage('terraform ended') {
            steps {
                sh 'echo "Ended....!!"'
            }
        }

        
    }
}

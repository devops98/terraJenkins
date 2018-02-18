
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
                sh 'sudo rm -r *;git clone https://github.com/devops98/terraJenkins.git'
            }
        }
       /* stage('tfsvars create'){
            steps {
                sh 'sudo cp /home/ec2-user/vars.tf ./jenkins/'
            }
        } */
	    
	stage('terraform mkdir') {
            steps {
                sh 'mkdir testdir; ls'
            }
        }
        stage('terraform init') {
            steps {
                sh 'ls;cd terraJenkins; terraform init -upgrade'
            }
        }
        stage('terraform plan') {
            steps {
                sh 'cd terraJenkins; terraform plan'
            }
        }
		
		stage('terraform apply') {
            steps {
                sh 'cd terraJenkins; terraform apply -auto-approve'
            }
        }
	    
     stage('terraform destroy') {
            steps {
                sh 'cd terraJenkins; terraform destroy -force'
            }
        }
		
        stage('terraform ended') {
            steps {
                sh 'echo "Ended....!!"'
            }
        }

	} 
    
    }

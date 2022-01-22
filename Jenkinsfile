pipeline {
	agent any 
	stages {
		stage ('clone the repo') {
			steps {
				echo "clone the repo"
 				sh 'rm -rf Testing'
				sh 'git clone https://github.com/Geeky-AYUSH/Testing.git'
				}
		}
		
		stage ('push repo to remote host') {
 			steps {
				echo "connect to remote host and pull down the latest version"
				sh '  ssh -i "/var/jenkins_home/workspace/kirti2.pem" ec2-user@ec2-13-126-73-102.ap-south-1.compute.amazonaws.com                                     sudo git -c /var/www/html pull'
				}
		}
	
		stage ('check website is up') {
			steps {
          			echo "check website is up"
 				sh   'curl -is | head -n 1'
				}
		}
  	}
}

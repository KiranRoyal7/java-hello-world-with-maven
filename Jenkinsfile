pipeline{
  agent any 
    stages{
       stage('Git Checkout'){
	       steps{
		       git credentialsId: 'db2e434e-c6c9-43a2-943d-786a2f63faba', url: 'https://github.com/jitpack/gradle-simple.git'
	       }
	}
	stage('Maven Build'){
	}
}
}


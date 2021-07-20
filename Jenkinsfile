pipeline{
  agent any 
    stages{
       stage('SCM'){
	       steps{
		       git credentialsId: 'db2e434e-c6c9-43a2-943d-786a2f63faba', url: 'https://github.com/jitpack/gradle-simple.git'
	       }
	}
	stage('Build'){
		steps{
			sh 'mvn --version'
		}
	}
	    stage('arti-server'){
		    steps{
			    rtServer (
			    id: 'artifact-ser',
			    url: 'https://wincywincy.jfrog.io/artifactory',
			    
			    credentialsId: 'Artifact-Creds',
			    
			    bypassProxy: true,
			    
			    timeout: 300
				    )

		    }
	     stage('upload'){
		     
		     steps{
			     rtUpload (
			     spec: '''{
			  "files": [
			    {
			      "pattern": "*.zip",
			      "target": "default-maven-local/"
			    }
			 ]
		    }''',

		    project: 'maven-2-default'
				     )
		     
		     
		     
		     }
		      
		    }
	    }
}
}


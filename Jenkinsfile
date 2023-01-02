pipeline {
  agent none
  
  stages{

	  stage("checkout"){
		  agent { label 'TestingServer' }
	
		  
		  steps {
			  sh "rm -rfd test_rb"
			withCredentials([usernamePassword(credentialsId: '2928978f-6e24-4e9d-b846-34fa23e4bca7', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
			    
			    sh('git clone https://${GIT_USERNAME}:${GIT_PASSWORD}@gitlab.com/ShimonDarshan/test_rb')
			    sh "ls"
			}

		  
		  }
	  
	  
	  
	  
	  }
	  
	  
    stage("build"){
      // when { branch 'main' }
      agent { label 'TestingServer' }
      
      steps{
        sh """
           echo $GIT_COMMIT
	   ls
	   pwd
	   cd test_rb
           docker-compose build
           """
	}

    }




}
}

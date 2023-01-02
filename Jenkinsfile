pipeline {
  agent none
  
  stages{

	  stage("checkout"){
		  agent { label 'TestingServer' }
	
		  
		  steps {
			withCredentials([usernamePassword(credentialsId: 'GitLab user', passwordVariable: 'GIT_PASSWORD', usernameVariable: 'GIT_USERNAME')]) {
			    
			    sh('git clone https://${GIT_USERNAME}:${GIT_PASSWORD}@')
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
           docker-compose build
           """
	}

    }




}
}

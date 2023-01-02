pipeline {
  agent none
  
  stages{

    stage("build"){
      // when { branch 'main' }
      agent { label 'TestingServer' }
      
      steps{
        sh """
           echo $GIT_COMMIT
           docker-compose build
           """
	}

    }




}
}

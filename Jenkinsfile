pipeline {
  agent none
  
  stages{

    stage("build"){
      when { branch 'testing' }
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

pipeline {
  agent any 
  environment {
    DOCKERHUB_CREDENTIALS = credentials('DCH')
  }
  stages {
    stage('Build') {
      steps { 
        echo 'Build Bundle-01'
	    sh ''' 
		      echo "We are started the build bundle process"
			  '''
		}
	}
	stage('Testing'){
	  steps {
	  echo 'Test Build-01'
	  sh '''
			echo "Test Build Started Now"
			ls -la
			'''
		}
	}
	stage('Deliver'){
	  steps {
		echo'Deliver Bundle'
		sh '''
  		touch hello.txt
		echo "Shelby Family" >>hello.txt
		docker build -t small-image .
  		echo "Deliver Process Completed"
		'''
	 stage('Login') {
      	   steps {
           sh ''' 
	   echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin 
		'''
      }
    }
		  }
	    }
      }
	
}
	

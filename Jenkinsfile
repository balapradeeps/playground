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
			  touch hello.txt
			  echo "Shelby Family" >>hello.txt
			  docker build -t balapradeeps/mini-image:v2 .
			  '''
		}
	}
	stage('Login'){
	  steps {
	  echo 'Login Process Started'
	  sh ''' 
	        echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin 
		'''
		}
	}
	stage('Push'){
      	  steps {
	  echo 'images pushing to dockerhub'	  
                sh ''' 
	        docker push balapradeeps/mini-image:v2 
		'''
      }
    }
	stage('Deliver'){
	  steps {
		echo'Deliver Bundle'
		sh '''
  		echo "Deliver Process Started and Completed"
		'''

		  }
	    }
      }
	
}
	

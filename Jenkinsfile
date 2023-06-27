pipeline {
  agent any 
  stages {
    stage('Build') {
      steps { 
        echo 'Build Bundel-01'
	    sh ''' 
		      echo "We are started the build bundel process"
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
		echo'Deliver Bundel'
		sh '''touch hello.txt
		echo "Shelby Family" >>hello.txt
		docker build -t small-image -f jenki/ .
		echo "Deliver Process Compleleted"
		'''
		  }
	    }
      }
	
}
	
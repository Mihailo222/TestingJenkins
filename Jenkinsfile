pipeline {

	agent { 
		label 'NodeFromRemote'
	   //	customWorkspace '/home/jenkins2/workspace/MyNewJobMika'
		}
	stages {

	stage('Checkout phase'){
		checkout scm
	}
	stage('Print Workspace'){
		steps {
			script {
			echo "Stage: ${STAGE_NAME}"
			echo "The current workspace is: ${env.WORKSPACE}"
				sh('ls -la')
			}
		}
		
	
	}
	}
}

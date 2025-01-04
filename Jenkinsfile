pipeline {

	agent { 
		label 'sshAgent'
	   	customWorkspace '/home/jenkins2/workspace/MyNewJobMika'
		}
	stages {

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

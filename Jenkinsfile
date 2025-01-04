pipeline {

	agent { 
		label 'NodeFromRemote'
	   //	customWorkspace '/home/jenkins2/workspace/MyNewJobMika'
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
post {
	always {
		script {
			cleanWs()
		}
		script {
			dir("${env.WORKSPACE}@tmp"){ 
			deleteDir()
			}
			dir("${env.WORKSPACE}@script"){ 
			deleteDir()
			}
			dir("${env.WORKSPACE}@lib"){ 
			deleteDir()
			}
			
		}
	}
	
}
}

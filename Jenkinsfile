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
	stage("Testing other agent"){
	agent { label 'sshAgent'}
	steps {
		script {
			sh('whoami')
		}
		
	}
	//dodatak brisanje foldera sa agenta2 u okviru ovog taska
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

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

	stage("delete a workspace's files and a directory!!!"){
	
		steps { //ovo mora u steps blok
		echo "Stage ${STAGE_NAME}"

		script {
		cleanWs()
		}
		}
	}

	stage("Deleting additional @tmp, @script and @lib files"){
	   steps {
		dir("${env.WORKSPACE}@tmp"){
			deleteDir()
		}
		script {
		 sh "ls -la ${env.WORKSPACE}@tmp"
		}
	   }
	}
}
}

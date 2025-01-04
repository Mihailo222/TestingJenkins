/*pipeline {

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
}*/

///***************************************************

/*pipeline {

        agent {

                label 'NodeFromRemote'

        }

        stages {
                stage('Test ansible versions'){
                        steps {
                                sh '''

                                ansible --version
                                ansible-playbook --version
                                ansible-galaxy --version
				'''
                        }
                }
        }
}*/

pipeline {
        agent {
		label 'NodeFromRemote'
		
	}
        stages {
                stage("Execute playbook"){

                steps {

                     ansiblePlaybook credentialsId: 'jenkinsansible','disableHostKeyChecking':true, installation:'Ansible',inventory:'/etc/ansible/hosts',playbook:'/etc/ansible/deployApp.yml'


                }



                }



        }

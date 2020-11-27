pipeline {

		agent any
	

        stages{
		
			stage('Checkout'){
        		steps{
					script {
						checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/utkshjn5/TestJenkins']]])
					}
        		}
        	}
			   	
        	
			
			
        	
        }
  }
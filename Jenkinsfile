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
		post {

				always {

					deleteDir()

				}

				success {

					emailext(
							mimeType: 'text/html',
							
							to: 'jainutkarsh@johndeere.com;mehtaom@johndeere.com',

							subject: "SUCCESSFUL: Jenkins Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",

							body: """<p>SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>

							<p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${

								env.BUILD_NUMBER

							}]</a>&QUOT;</p>""",

							recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']]

					)

				}

				failure {

					emailext(
							mimeType: 'text/html',
							
							to: 'jainutkarsh@johndeere.com;,

							subject: "FAILED: Jenkins Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",

							body: """<p>FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]':</p>

							<p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${

								env.BUILD_NUMBER

							}]</a>&QUOT;</p>""",

							recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']]

					)

				}

        }
  }

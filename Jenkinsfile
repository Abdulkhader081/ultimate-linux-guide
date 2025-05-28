pipeline { 
	agent any 
		parameters { string(name: 'USERNAME_PARAM', description: 'Username for credentials') string(name: 'PASSWORD_PARAM', description: 'Password for credentials') string(name: 'CREDENTIALS_ID_PARAM', description: 'ID for credentials') string(name: 'DESCRIPTION_PARAM', description: 'Description for credentials')}
			stages { 
				stage('Create Credentials') { 
					steps { 
						script { 
              createCredentials(params.USERNAME_PARAM, params.PASSWORD_PARAM, params.CREDENTIALS_ID_PARAM, params.DESCRIPTION_PARAM)
							} 
						}
					} 
				} 
			} 
	
	def createCredentials(username, password, credentialsId, description) { 
	def apiUrl = "http://your-jenkins-url/credentials/store/system/domain/_/createCredentials" 
	// Create XML payload for the credentials without $class 
	def credentialsXml = """ GLOBAL ${credentialsId} ${description} ${username} ${password} """ 
	// Use curl to create credentials 
	sh "curl -X POST -u your-jenkins-username:your-jenkins-api-token -H 'Content-Type: application/xml' -d '${credentialsXml}' ${apiUrl}" 
	}

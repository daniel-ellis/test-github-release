node('git') {

	stage ('Checkout') {
    	checkout scm
  	}

  	stage ('Release') {
		withCredentials([[$class: 'StringBinding', credentialsId: '03a932ce-06c6-494e-9da2-809f9e797c18', variable: 'accessToken']]) {

	        gitHubRelease organisation: "daniel-ellis",
	                project: 'test-github-release',
	                version: "release name",
	                accessToken: "${env.accessToken}",
	                assets: ["Artifact"],
	                release: false,
	                targetCommit: "master"
    	}
  	}

}
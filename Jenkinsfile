node('git') {

	stage ('Checkout') {
    	checkout scm
  	}

  	stage ('Release') {
		withCredentials([[$class: 'StringBinding', credentialsId: '03a932ce-06c6-494e-9da2-809f9e797c18', variable: 'accessToken']]) {

	        gitHubRelease organisation: "daniel-ellis",
	                project: 'test-github-release',
	                version: "release-name.${env.BUILD_NUMBER}",
	                accessToken: "${env.accessToken}",
	                assets: ["/Users/danellis/Desktop/tmpworkspace/nodeworkspace/workspace/test-release_master/folder/Artifact", "/Users/danellis/Desktop/tmpworkspace/nodeworkspace/workspace/test-release_master/folder/Artifact2"],
	                release: false,
	                targetCommit: "master"
    	}
  	}

}
pipeline {
	agent {label "linux"}
	options {
		buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')
		disableConcurrentBuilds()
	}
	stages {
		stage("Hello") {
			steps {
				echo "hello"
			}
		}
		stage("cat README.md") {
			when {
				branch "fix-*"
			}
			steps {
				sh '''
					cat README.md
				'''
			}
		}
	}
}

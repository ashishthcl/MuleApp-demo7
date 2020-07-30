pipeline {
	agent any
	stages {
		stage ('Unit Test') {
			steps {
				sh 'mvn -X clean test'
			}
		}
		stage ('Deploy CloudHub'){
			environment {
				ASH_BLOG_MULE_CRED = credentials('anypoint.credentials')
			}
			steps {
				sh 'mvn clean install deploy -DmuleDeploy -Danypoint.username=${ASH_BLOG_MULE_CRED_USR} -Danypoint.password=${ASH_BLOG_MULE_CRED_PSW}'
			}
		}
	}
}

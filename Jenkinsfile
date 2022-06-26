pipeline {
  agent any
  tools {
    maven 'maven'
  }
  parameters {
    string(name: 'VERSION', defaltValue: '', description: '')
	choice(name: 'VERSION', choices: ['1.1', '1.2', '1.3'], description: '')
	booleanParam(name: 'executeTests', defaultValue: true, description: '')
  }
  environment {
    NEW_VERSION = '1.3.0'
	SERVER_CREDENTIALS = credentails('CREDENTIALID')
  }
  stages {
    stage("build") {
      steps {
        echo 'building the application..'
		echo "building version ${NEW_VERSION}"
      }
    }
    stage("test") {
      when {
	    expression {
		  params.executeTests
		}
	  }
	  steps {
        echo 'testing the application'
      }
    }
    stage("deploy") {
      steps {
        echo 'testing the application'
        echo "deploying version $params.VERSION"
      }
    }
  }
  post {
    always {
      //
    }
    success {
      //
    }
    failure {
      //
    }
  }
}

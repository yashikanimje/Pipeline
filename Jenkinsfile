pipeline {
    agent any
	parameters {
	 choice ( name: 'Parameter', choices: ['DEV', 'QA', 'UAT'], description: 'Pick Environment value')
	}

    stages {
         stage('Checkout') {
            steps {
                checkout scm
		}
	 }
         stage('Compile and Build') {
            steps {
                sh 'mvn install'
                }
                }
         
	stage('Deployment'){
		    steps {
			script {
			 if ( "${env.Parameter}" == 'QA' ){
        	sh 'cp target/Pipeline.war /home/yashika/Documents/devtool/apache-tomcat-9.0.93/webapps'

        	echo "deployment has been done on QA!"
			 }
			else if ( "${env.Parameter}" == 'UAT' ){
        	sh 'cp target/Pipeline.war /home/yashika/Documents/devtool/apache-tomcat-9.0.93/webapps'

    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
		}
	    }
	}
    }
}

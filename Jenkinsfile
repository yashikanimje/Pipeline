pipeline{
      agent any
      
          parameters {
              choice choices: ['DEV', 'QA', 'UAT'], description: 'Choice parameter', name: 'ENVIRONMENT'
                     }

            stages{
                  stage(checkout){
                        steps{
                            checkout scm
                              }
                        }
               stage(build){
                     steps{
                       sh 'mvn install'
                        }
                       }
                  stage(DDDDEPLOYYYYYMENT){
                        steps{
 				script {
			 if ( "${env.ENVIRONMENT}" == 'QA' ){
        	sh 'cp target/Project-2.war /home/yashika/Documents/devtool/apache-tomcat-9.0.93/webapps'
        	echo "deployment has been done on QA!"
			 }
			elif ( "${env.ENVIRONMENT}" == 'UAT' ){
    		sh 'cp target/Project-2.war /home/yashika/Documents/devtool/apache-tomcat-9.0.93/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			fi                             

                        }
                  }
    }
}


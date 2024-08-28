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
        	sh 'cp target/Pipeline.war /home/yashika/Documents/devtool/apache-tomcat-9.0.93/webapps'
        	echo "deployment has been done on QA!"
			 }
			else if ( "${env.ENVIRONMENT}" == 'UAT' ){
    		sh 'cp target/Pipeline.war /home/yashika/Documents/devtool/apache-tomcat-9.0.93/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			fi                             

                        }
                  }
    }
}
}

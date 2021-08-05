pipeline {
    agent any

    tools {
        maven "maven"
	
    }
    
   parameters {
        string(name: 'company', defaultValue: 'Sapient', description: 'Enter your cmopany name???')
	booleanParam(name: 'DEBUG_BUILD', defaultValue: true, description: 'do you want to buidl with debug')
	choice(name: 'env', choices: ['DEV', 'TEST', 'PROD'], description: 'specify you build env') 
    }

    stages {
        stage('Build') {
            steps {
		echo "The company name ${params.company}"
		echo "BUILD ENV : ${params.env}"
		echo "BUILD_WITH DEBUG : ${params.DEBUG_BUILD}"

                echo "************** Running ${env.BUILD_ID} on ${env.JENKINS_URL}***********"


                git 'https://github.com/Akhil7042/sapient-freshers-2021-jun-asde.git'

                // Run Maven on a Unix agent.
              //  bat  "mvn -Dmaven.test.failure.ignore=true clean package"
                 script {
                 
                    try{
                        
                    if (params.env == 'PROD') {
                        echo 'Inside prod environment'
                    } else {
                        echo 'Inside Dev environment'
                    }
                      
                    
                    }catch(error){
                       throw error
                    }
                    
                    
                 

		}
            }

            }
        }

  post {
        failure {
		echo "Application failed ***********" 
        }

    }    

}


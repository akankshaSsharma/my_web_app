pipeline{

      agent {
                docker {
                image 'maven'
                args '-v $HOME/.m2:/root/.m2'
                }
            }
        
        stages{

		stage('Quality Gate Status Check'){
			steps{
			      withSonarQubeEnv('sonarserver') { 
			      sh "mvn sonar:sonar"
                       	     	}
			}
      		}
		    	   
		stage('Build')
		{
			steps{
			sh "mvn clean install"
		  
                 	}
		}
	}
}
           

pipeline{

      agent {
                docker {
                image 'maven'
                args '-v $HOME/.m2:/root/.m2'
                }
            }
        
        stages{

		stage('Quality Gate Status Check'){
			      withSonarQubeEnv('sonarserver') { 
			      sh "mvn sonar:sonar"
                       	     	}
      		}
		    	   
		stage('Build')
		{
			sh "mvn clean install"
		  
                 	}
	}
}
           

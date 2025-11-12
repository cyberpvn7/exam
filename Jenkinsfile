pipeline {
    agent any

    stages { 
        stage('pull') {
            steps {
               cleanWs()
	       echo "pull repo"
 	       sh "git clone https://github.com/cyberpvn7/exam"
		   sh "cd exam/"
		   // withCreadentials(
			  //  [usernamePassword(
			  //  	credentialsId:'dockercred',
			  //  	usernameVarible:'dock',
			  //  	passwordVarible:'dock_pass'
		   // 	)]){
     //       	   sh """
				 //   echo "$dock_pass" | docker login -u "$dock" --password-stdin
			  //  """
				
				sh "pwd"
				sh "docker build -t pavank28/apan_py:latest ./exam"
		        sh "docker run  pavank28/apan_py:latest"

				withCredentials([usernamePassword(
                    credentialsId:"dockercred",
                    usernameVariable:"dockerHubUser", 
                    passwordVariable:"dockerHubPass")]){
                sh 'echo $dockerHubPass | docker login -u $dockerHubUser --password-stdin'
					sh "docker push pavank28/apan_py:latest"
				}
	        
			}
        }
    }
}

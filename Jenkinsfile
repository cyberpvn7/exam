pipeline {
    agent any
    stages { 
        stage('pull') {
            steps {
                cleanWs()
	      		echo "pull repo"
 	            sh "git clone https://github.com/cyberpvn7/exam" //change it
		        sh "cd exam/" // change it
				sh "docker build -t pavank28/apan_py:latest ./exam"
		        sh "docker run  pavank28/apan_py:latest"

				withCredentials([usernamePassword(
                    credentialsId:"dockercred", // change it
                    usernameVariable:"dockerHubUser", 
                    passwordVariable:"dockerHubPass")]){
                sh 'echo $dockerHubPass | docker login -u $dockerHubUser --password-stdin'
					sh "docker push pavank28/apan_py:latest"
				}
			}
        }
    }
}

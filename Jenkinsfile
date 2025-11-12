pipeline {
    agent any

    stages { 
        stage('pull') {
            steps {
               cleanWs()
	       echo "pull repo"
 	       sh "git clone https://github.com/cyberpvn7/exam"    
            }
        }
    }
}

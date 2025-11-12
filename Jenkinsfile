pipeline {
    agent any

    stages { 
        stage('pull') {
            steps {
               cleanWs()
	       echo "pull repo"
 	       sh "git pull https://github.com/cyberpvn7/exam"    
            }
        }
    }
}

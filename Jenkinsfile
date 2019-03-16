node {
      stage('Pull code from Git Repo') { // for display purposes
      // Get some code from a GitHub repository
      git credentialsId: 'github1', url: 'https://github.com/sumeet-devops/centos7docker.git'
                                        }
      
     
   stage('Docker build')
        {
       sh '/usr/bin/docker build -t sumeetdhaliwal/centos7docker:latest .'
        }

    stage('Docker Push')
    {

withCredentials([usernamePassword(credentialsId: 'docker1', passwordVariable: 'dockerpwd', usernameVariable: 'dockeruser')]) 
	    {
    		sh '/usr/bin/docker login -u $dockeruser -p $dockerpwd'
            }

	sh '/usr/bin/docker push sumeetdhaliwal/centos7docker:latest'
    }   
   }


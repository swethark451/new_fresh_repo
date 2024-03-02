pipeline {
    agent any 
    stages {
      
        stage("clone code") {
            steps {
                script {
                    // Let's clone the source
                    git branch: 'main', credentialsId: 'git-credentials', url: 'https://github.com/swethark451/new_fresh_repo'

                }
            }
        }
        stage("build") {
            steps { 
                sh "docker build -t flask . "
            }
        }
        
        stage("deploy") {
          steps{
            sh "docker-compose down && sudo docker-compose up -d "
          }
        }
      
    }
}

    



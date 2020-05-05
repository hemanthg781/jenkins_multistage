pipeline {
      agent any
      stages {
            stage('Init') {
                  steps {
                        echo 'Hi Hemanth, this is DEV Stage'
                        
                  }
            }
            stage('Build') {
                  steps {
                        echo 'Hi Hemanth, this is UAT Stage'
                  }
            }
            stage('Deploy') {
                  steps {
                        echo "Hi Hemanth, this is PROD Stage"
                  }
            }
            
            stage('Publish') {
                   when {
                         branch 'master'
                        }
                   steps {
                          withDockerRegistry([ credentialsId: "dockerlogin", url: "" ]) {
                          sh 'docker push hemanthg781/terraform:latest'
                          sh 'docker push hemanthg781/cli:latest'
        }
      }
    }
      }
}

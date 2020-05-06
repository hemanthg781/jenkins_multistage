pipeline {
      agent any
      stages {
            stage('DEV') {
                  steps {
                        echo 'Hi Hemanth, this is DEV Stage'
                        
                  }
                  stage('DEV1') {
                  steps {
                        echo 'Hi Hemanth, this is DEV1 Stage'
                        
                  }
                  
         
            }
            stage('UAT') {
                  steps {
                        echo 'Hi Hemanth, this is UAT Stage'
                  }
            }
            stage('PROD') {
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
      
      post {
        always {
            emailext body: 'A Test EMail - Build is success', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}

pipeline {
    agent none

    stages {
        stage("build and test the project") {
            agent {
                docker "our-build-tools-image"
            }
            stages {
               stage("build") {
                   steps {
                       echo 'Hi Hemanth, this is build Stage'
                   }
               }
               stage("test") {
                   steps {
                      echo 'Hi Hemanth, this is test Stage'
                   }
               }
            }
            post {
                success {
                    stash name: "artifacts", includes: "artifacts/**/*"
                }
            }
        }

        stage("deploy the artifacts if a user confirms") {
            input {
                message "Should we deploy the project?"
            }
            agent {
                docker "our-deploy-tools-image"
            }
            steps {
                echo 'Hi Hemanth, this is deploy Stage'
            }
        }
    }
}

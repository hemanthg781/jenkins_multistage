pipeline {
    agent any

    stages {
        stage("build and test the project") {
            stage("build") {
                   steps {
                       echo 'Hi Hemanth, this is build Stage'
                   }
               }
            stages {
               stage("build1") {
                   steps {
                       echo 'Hi Hemanth, this is build1 Stage'
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

pipeline {
    agent any

    stages {
        stage("build and deploy on Windows and Linux") {
            parallel {
                stage("windows") {
                    agent {
                        label "any"
                    }
                    stages {
                        stage("build") {
                            steps {
                                echo 'Hi Hemanth, run build.bat'
                            }
                        }
                        stage("deploy") {
                            when {
                                branch "master"
                            }
                            steps {
                               echo 'Hi Hemanth, run deploy.bat'
                            }
                        }
                    }
                }

                stage("linux") {
                    agent {
                        label "any"
                    }
                    stages {
                        stage("build") {
                            steps {
                                echo 'Hi Hemanth, run build.s'
                            }
                        }
                        stage("deploy") {
                             when {
                                 branch "master"
                             }
                             steps {
                                echo 'Hi Hemanth, run deploy.sh'
                            }
                        }
                    }
                }
            }
        }
    }
}

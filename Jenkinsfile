pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                   echo 'Running under $STAGE_NAME'
                    def response = httpRequest 'https://api.github.com/repos/jenkinsci/jenkins/pulls'
                    jsonobj = readJSON text: "${response.content}"
                    jsonobj.each {
                        def PR1 = "${it}"
                        it.each
                            if(it.state == "open") {
                            echo "${it.title}"
                        }
                    }
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Running under $STAGE_NAME'
            }
        }
        stage('Deliver') {
            steps {
                echo 'Running under $STAGE_NAME'
            }
        }
    }      
}

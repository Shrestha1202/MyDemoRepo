pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    echo "${STAGE_NAME}"
                    def client_id = "4ddd5dc8b5d4422f80826d09b40d3ac8"
                    def redirect_uri = "https://www.google.com"
                    redirect_uri= java.net.URLEncoder.encode(redirect_uri, "UTF-8")
                    echo "${redirect_uri}"
                    def response = httpRequest consoleLogResponseBody: true, responseHandle: 'NONE', url: """https://accounts.spotify.com/authorize?client_id=${client_id}&response_type=code&redirect_uri=${redirect_uri}&scope=user-read-private%20user-read-email""", wrapAsMultipart: false
                    echo response.content
                        }
                        
                    }
                }
            
        
        stage('Test') {
            steps {
                echo "Running under ${STAGE_NAME}"
            }
        }
        stage('Deliver') {
            steps {
                echo "Running under ${STAGE_NAME}"
            }
        }
    }      
}

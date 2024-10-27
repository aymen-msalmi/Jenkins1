pipeline {
    agent {
        docker {
            image 'node:21-alpine'
        }
    }

    stages {
        stage('build') {
            steps {
                sh 'npm -v'
                echo "done installing"
            }
        }
    }

    post {
        always {
            echo 'always !'
            emailext (to: 'aymen.msalmi@esprit.tn', body: '$DEFAULT_CONTENT',jubject:'$DEFAULT_SUBJECT' )
            echo 'email sent !'
        }
        success {
            echo 'success !'
        }
    }

}

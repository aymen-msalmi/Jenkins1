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
            emailext (to: 'aymen.msalmi@esprit.tn',cc :'msalmi.aymen.89@gmail.com' ,body: '$DEFAULT_CONTENT',subject:'$DEFAULT_SUBJECT' )
            echo 'email sent !'
        }
        success {
            echo 'success !'
        }
    }

}

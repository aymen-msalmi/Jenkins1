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
            emailext body: 'Build finished', subject: 'Build Status', to: 'aymen.msalmi@esprit.tn
        }
        success {
            echo 'success !'
        }
    }

}

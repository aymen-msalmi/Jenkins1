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
             mail to: 'aymen.msalmi@esprit.tn',
                 subject: "Push effectué : Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' terminé",
                 body: """
                Un push a été effectué sur le dépôt GitHub et le build a été déclenché.
 
                Détails :
                Job : ${env.JOB_NAME}
                Build Number : ${env.BUILD_NUMBER}
                Build Status : ${currentBuild.currentResult}
                Commit : ${env.GIT_COMMIT}
 
                Consultez le build : ${env.BUILD_URL}
                """
            echo 'email sent !'
        }
        success {
            echo 'success !'
        }
    }

}

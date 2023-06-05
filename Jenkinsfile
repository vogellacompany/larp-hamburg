pipeline {
    agent any

    stages {
        stage('Deploy') {
            stages {
                stage('Deploy to server') {
                    steps {
                        sh 'rsync -rzvhP --delete _site/* jenkins@gilbert.vogella.com:/var/www/vhosts/larp-hamburg/staging'
                        sh 'ssh jenkins@gilbert.vogella.com rsync -rzvhP --delete /var/www/vhosts/larp-hamburg/staging/* /var/www/vhosts/larp-hamburg/www/'
                    }
                }
            }
        }
    }

    post {
        failure {
            mail to: 'Lars.Vogel@vogella.com', subject: 'Blog deploy failed', body: 'Please fix!'
        }
    }
}
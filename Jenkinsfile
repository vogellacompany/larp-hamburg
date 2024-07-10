pipeline {
    agent any

    parameters {
        string(name: 'REMOTE_SERVER', defaultValue: 'gilbert.vogella.com', description: 'Remote server to deploy to')
    }

    stages {
        stage('Deploy') {
            stages {
                stage('Deploy to server') {
                    steps {
                        def remoteUser = 'jenkins'
                        def remoteServer = "${remoteUser}@${params.REMOTE_SERVER}"

                        sh "rsync -rzvhP --delete _site/* ${remoteServer}:/var/www/vhosts/larp-hamburg/staging"
                        sh "ssh ${remoteServer} rsync -rzvhP --delete /var/www/vhosts/larp-hamburg/staging/* /var/www/vhosts/larp-hamburg/www/"
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
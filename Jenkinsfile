pipeline {
    agent {
        docker {
            image 'node:12.13.0'
            args '-u root:sudo -v /var/run/docker.sock:/var/run/docker.sock -v /usr/bin/docker:/usr/bin/docker'
        }
    }
    environment {
        HOME = '.'
    }

    options {
      buildDiscarder(logRotator(numToKeepStr: '5'))
    }    

    stages {
        stage('Checkout'){
            steps {
                checkout scm
            }
        }

        stage('NPM Install'){
            steps {
                sh 'npm install'
                sh 'npm install -g @angular/cli'
            }
        }

        stage('NG Build'){
            steps {
                sh 'ng build --prod'
            }
        }

        stage('NG Build'){
            steps {
                sh 'echo Hello'
            }
        }

    }    
}
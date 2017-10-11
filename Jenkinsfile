pipeline {
    agent {
        docker { image 'ruby:2.4.1' }
    }
    stages {
        stage('Clone the repo') {
            steps {
                checkout scm
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'gem install bundler'
                sh 'bundle install'
            }
        }
    }
}

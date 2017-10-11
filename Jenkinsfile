agent {
    docker { image 'ruby:2.4.1' }
}
stages {
    stage('Cloning the repo') {
        steps {
            checkout scm
        }
    }
    stage('Installing dependencies') {
        steps {
            sh 'gem install bundler'
            sh 'bundle install'
        }
    }
    stage('Building the devdocs site') {
        steps {
            sh 'jekyll build'
        }
    }
}

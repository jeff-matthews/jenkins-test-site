node {
    stage('Build') {

        checkout scm

        docker.image('ruby:2.4.1').inside {

          stage("Install dependencies") {
            sh 'gem install bundler'
            sh 'bundle install'
          }

          stage("Build the devdocs site") {
            sh 'jekyll build'
          }

       }

    }

    stage('Archive') {
        archive '_site/**'
        stash includes: '_site/**', name: 'devdocs'
    }

    stage('Deploy') {
        //some commands
    }
}

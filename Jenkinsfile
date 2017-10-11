node {
    stage("Main build") {

        deleteDir()

        checkout scm

        docker.image('ruby:2.4.1').inside {

          stage("Install Bundler") {
            sh "gem install bundler --no-rdoc --no-ri"
          }

          stage("Use Bundler to install dependencies") {
            sh "bundle install"
          }

          stage("Build package") {
            sh "jekyll build"
          }

       }

    }

}

node {
    stage("Preparing the build environment") {

        deleteDir("Cleaning up the workspace")

        checkout scm("Cloning the repo`")

        docker.image('ruby:2.4.1').inside {

          stage("Installing bundler") {
            sh "gem install bundler --no-rdoc --no-ri"
          }

          stage("Installing dependencies") {
            sh "bundle install"
          }

          stage("Building the site") {
            sh "jekyll build"
          }

       }

    }

}

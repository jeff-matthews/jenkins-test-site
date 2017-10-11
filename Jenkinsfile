node {
    stage("Main build") {

        deleteDir()

        checkout scm

        docker.image('ruby:2.4.1').inside {

          stage("Install bundler") {
            sh "gem install bundler"
          }

          stage("Install dependencies") {
            sh "bundle install"
          }

          stage("Build package") {
            sh "jekyll build"
          }

       }

    }

}

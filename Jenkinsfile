node('docker') {

  stage 'Checkout'
  checkout scm

  def buildEnv = docker.image('ruby:latest')
  buildEnv.pull()
  buildEnv.inside {
    stage 'Install dependencies'
    sh 'gem install bundler'
    sh 'bundle install'

    stage 'Build'
    sh 'jekyll build'
  }
}

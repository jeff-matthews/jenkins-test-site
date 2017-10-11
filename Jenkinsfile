node('docker') {
  deleteDir()

  stage 'Checkout'
  checkout scm

  def buildEnv = docker.image('ruby:2.4.1')
  buildEnv.pull()
  buildEnv.inside {
    stage 'Install dependencies'
    sh 'gem install bundler'
    sh 'bundle install'

    stage 'Build'
    sh 'jekyll build'
  }
}

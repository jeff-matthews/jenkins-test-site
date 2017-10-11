node {
  deleteDir()

  checkout scm

  stage('Ruby Gems') {
    sh 'command curl -sSL https://rvm.io/mpapis.asc | gpg --import -'
    sh 'curl -sSL https://get.rvm.io | bash -s stable'
    sh 'gem install bundler'
    sh 'bundle install'
  }
}

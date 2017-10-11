node {
  deleteDir()

  checkout scm

  stages {
    stage('RVM') {
      sh '\curl -sSL https://get.rvm.io | bash -s stable --ruby'
    }
    stage('Ruby Gems') {
      sh 'gem install bundler --no-ri --no-rdoc'
      sh 'bundle install'
    }
  }
}

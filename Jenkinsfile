agent {
    docker {
        image 'ruby:2.4.1'
    }
        stages {
            stage('Check ruby') {
                steps {
                    sh 'ruby --version'
                }
            }
            stage('Clone the repo') {
                steps {
                    git branch: 'master', url: 'https://github.com/jeff-matthews/jenkins-test-site.git'
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

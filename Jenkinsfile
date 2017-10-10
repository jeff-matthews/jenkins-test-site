#!/usr/bin/env groovy

node(){
    stage("rvm"){
        sh "source ~/.rvm/scripts/rvm && rvm use --install --create ruby@2.4.1 && export > rvm.env"
        sh "gem install bundler"
        sh "bundle install"
    }
}

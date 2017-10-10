#!/usr/bin/env groovy

node(){
    stage("rvm"){
        sh "test -f ~/.rvm/scripts/rvm"
            sh "source ~/.rvm/scripts/rvm && rvm use --install --create 2.3.3 && export > rvm.env"
            sh "gem install bundler"
            sh "bundle install"
    }
}

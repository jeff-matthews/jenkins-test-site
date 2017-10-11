stage ('Stage 1. Allocate workspace')
def extWorkspace = exwsAllocate 'diskpool1'

node {
    exws (extWorkspace) {
        stage('Stage 2. Build the site') {

            checkout scm

            docker.image('ruby:2.4.1').inside {

              stage("Install dependencies") {
                sh 'gem install bundler'
                sh 'bundle install'
              }

              stage("Build the devdocs site") {
                sh 'jekyll build'
              }
           }
        }
    }
}

node {
    exws (extWorkspace) {
        stage('Stage 3. Deploy files')

        sh 'git config --global user.email "<email>"'
        sh 'git config --global user.name "<username>"'

        def dateFormat = new SimpleDateFormat("yyyy-MM-dd HH:mm")
        def date = new Date()

        sh('git checkout gh-pages')
        sh('git add .')
        sh('git commit -m "Site updated at '+dateFormat.format(date)+'"')

        withCredentials([usernamePassword(credentialsId: 'github', passwordVariable: 'GH_TOKEN', usernameVariable: 'GH_USER')]) {
            sh 'git push https://${GH_USER}:${GH_TOKEN}@github.com/magento/devdocs.git gh-pages'v
        }
    }
}

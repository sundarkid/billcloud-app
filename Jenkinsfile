node {
  deleteDir
  checkout scm
  echo 'beginnning workflow...'

  stage 'test'
  echo 'do some rspec testing'
  sh '''#!/bin/bash
  source /usr/local/rvm/scripts/rvm
  bundle install --path=.bundle/gems/
  bundle exec rake spec
  '''

  stage 'deploy'
  echo 'deploy to puppet masters'
}

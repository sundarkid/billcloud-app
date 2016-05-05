node {
  checkout scm
  echo 'beginnning workflow...'

  stage 'test'
  echo 'do some rspec testing'
  sh '''#!/bin/bash
  source ~/.rvm/scripts/rvm
  ruby -v
  bundle install --path=.bundle/gems/
  bundle exec rake spec
  '''

  stage 'deploy'
  echo 'deploy to puppet masters'
}

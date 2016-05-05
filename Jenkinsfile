node {
  checkout scm
  echo 'beginnning workflow...'

  stage 'test'
  echo 'do some rspec testing'
  sh '''#!/bin/bash
  source ~/.rvm/scripts/rvm
  ruby -v
  bundle install --path=.bundle/gems/
  '''

  stage 'deploy'
  echo 'deploy to puppet masters'
}

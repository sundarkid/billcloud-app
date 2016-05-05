node {
  checkout scm
  echo 'beginnning workflow...'

  stage 'test'
  echo 'do some rspec testing'
  sh '''#!/bin/bash
  CURRDIR=`pwd`
  echo "working directory: $CURRDIR"
  source source /usr/local/rvm/scripts/rvm
  ruby -v
  bundle install --path=.bundle/gems/
  bundle exec rake spec
  '''

  stage 'deploy'
  echo 'deploy to puppet masters'
}

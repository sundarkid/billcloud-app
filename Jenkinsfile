node {
  deleteDir()
  checkout scm
  echo 'beginnning workflow...'

  stage 'syntax testing'
  sh '''#!/bin/bash
  source ~/.rvm/scripts/rvm
  puppet parser validate manifests/
  '''

  stage 'rspec testing'
  sh '''#!/bin/bash
  source ~/.rvm/scripts/rvm
  bundle install --path=.bundle/gems/
  bundle exec rake spec
  '''

  stage 'deploy'
  echo 'deploy to puppet masters'
}

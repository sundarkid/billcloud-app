node {
  deleteDir()
  checkout scm
  echo 'beginnning workflow...'

  stage 'prepare gems'
  sh '''#!/bin/bash
  source ~/.rvm/scripts/rvm
  bundle install --path=.bundle/gems/
  '''

  stage 'syntax testing'
  sh '''#!/bin/bash
  bundle exec puppet parser validate manifests/
  '''

  stage 'rspec testing'
  sh '''#!/bin/bash
  bundle exec rake spec
  '''

  stage 'deploy'
  echo 'deploy to puppet masters'
}

node {
  checkout scm
  echo 'beginnning workflow...'

  stage 'test'
  echo 'do some rspec testing'
  sh '''#!/bin/bash
  whoami
  source ~/.rvm/scripts/rvm
  ruby -v
  '''

  stage 'deploy'
  echo 'deploy to puppet masters'
}

node {
  deleteDir()
  checkout scm
  echo 'beginnning workflow...'

  stage 'prepare gems'
  sh '''#!/bin/bash
  /usr/local/rvm/gems/ruby-2.4.1/wrappers/bundle install --path=.bundle/gems/
  '''

  stage 'syntax testing'
  sh '''#!/bin/bash
  /usr/local/rvm/gems/ruby-2.4.1/wrappers/bundle exec puppet parser validate manifests/
  '''

  stage 'lint testing'
  sh '''#!/bin/bash
  /usr/local/rvm/gems/ruby-2.4.1/wrappers/bundle exec bundle exec puppet-lint --no-autoloader_layout-check manifests/*.pp
  '''

  stage 'rspec testing'
  sh '''#!/bin/bash
  /usr/local/rvm/gems/ruby-2.4.1/wrappers/bundle exec rake spec
  '''

  stage 'smoke testing'
  sh '''#!/bin/bash
  /usr/local/rvm/gems/ruby-2.4.1/wrappers/bundle exec rake spec_prep
  puppet apply tests/init.pp --noop --modulepath=spec/fixtures/modules
  '''

  stage 'deploy'
  echo 'deploy to puppet masters'
}

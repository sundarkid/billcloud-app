node {
  checkout scm
  echo 'beginnning workflow...'

  stage 'test'
  echo 'do some rspec testing'
  sh """
    #!/bin/bash
    source .rvm/scripts/rvm
    ruby -v
  """

  stage 'deploy'
  echo 'deploy to puppet masters'
}

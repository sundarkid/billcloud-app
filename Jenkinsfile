node {
  checkout scm
  echo 'beginnning workflow...'

  stage 'test'
  echo 'do some rspec testing'
  sh """
    #!/bin/bash
    source /usr/local/rvm/scripts/rvm
  """

  stage 'deploy'
  echo 'deploy to puppet masters'
}

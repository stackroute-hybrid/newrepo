node {
  stage 'Checkout Repository'
  git url: 'https://github.com/stackroute/sample-ci-project.git', branch: 'integration'

  stage 'Installing Dependencies'
  sh "npm prune"
  sh "npm install"

  stage 'Testing'
  sh "npm test"

  stage 'Build'
  sh "rm dist -rf"
  sh "mkdir dist -p"
  sh "cp package.json dist && cd dist && tar cvzf my-ci-project_current.tar.gz *"
  step([$class: 'ArtifactArchiver', artifacts: 'dist/*.tar.gz', fingerprint: true])
}
Contact GitHub API Training Shop Blog About
© 2016 GitHub, Inc. Terms Privacy Security Status Help

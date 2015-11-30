node {
  stage 'Build'
  sh 'sleep 2'
  echo 'Built successfully'

  stage 'Test'
  parallel(
    integrationTests: {
      sh 'echo completed selenium test'
    }, sonarAnalysis: {
      sh 'echo completed sonar test'
    }, failFast: true
  )
  checkpoint 'Before deployment'

  stage 'Deploy'
  input 'Do you want to deploy?'
  echo 'Workflow rocks'
}

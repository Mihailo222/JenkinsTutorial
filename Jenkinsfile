pipeline {
 agent { label 'agent1' }
 stages {
  stage('test'){
   steps {
    sh '''
       gcloud version
    '''
   }
  }
 }
}

pipeline {
 agent { label 'agent1' }
 environment {
  CLOUDSDK_CORE_PROJECT='project_name' //gcloud env var u koji se smesta project_name
 }
 stages {
  withCredentials([file(credentialsId: 'gcloud-creds', variable: 'GCLOUD_CREDS')]) //u varijablu GCLOUD_CREDS (env var) se smesta vrednost .json fajla 
  //gcloud-creds je Jenkins credential u koji je smesten .json fajl
  stage('test'){
   steps {
    sh '''
       gcloud version
       gcloud auth activate-service-account --key-file="$GCLOUD_CREDS" 
       gcloud compute zones list
    '''
   }
  }
 }
}

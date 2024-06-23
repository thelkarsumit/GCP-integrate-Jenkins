pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        withCredentials([file(credentialsId: 'GCP-service-key', variable: 'GCLOUD_CREDS')]) {
          sh '''
            gcloud version
            gcloud auth activate-service-account --key-file="$GCP-service-key"
            gcloud compute zones list
          '''
        }
      }
    }
  }
}

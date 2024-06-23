pipeline {
  agent any
    environment {
    CLOUDSDK_CORE_PROJECT='peak-axiom-426310-b1'
  }
  stages {
    stage('test') {
      steps {
        withCredentials([file(credentialsId: 'GCP-service-key', variable: 'GCLOUD_CREDS')]) {
          sh '''
            gcloud version
            gcloud auth activate-service-account --key-file="$GCLOUD_CREDS"
            gcloud compute zones list
          '''
        }
      }
    }
  }
}

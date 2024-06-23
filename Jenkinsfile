pipeline {
  agent any
    environment {
    CLOUDSDK_CORE_PROJECT='peak-axiom-426310-b1'
    CLIENT_EMAIL='jenkins-vm-controller@peak-axiom-426310-b1.iam.gserviceaccount.com'
    GCLOUD_CREDS=credentials('GCP-service-key')
  }
  stages {
    stage('test') {
      steps {
          sh '''
          gcloud version
          gcloud auth activate-service-account --key-file="$GCLOUD_CREDS"
          gcloud compute zones list
          '''
        }
      }
    }
    post {
    always {
      sh 'gcloud auth revoke $CLIENT_EMAIL'
    }
  }
}

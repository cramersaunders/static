pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World again"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }  
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-west-2',credentials:'aws-static') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'robertsproject3s3bucket')
                  }
              }
         }
     }
}

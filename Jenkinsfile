pipeline {
     agent any
     stages {
          stage ('Upload to AWS') {
               steps {
                    withAWS(region:'us-west-1', credentials: 'aws-static'){
					    //do something
						s3upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'robertsproject3s3bucket')
					}                   
               }
          }
     }
}

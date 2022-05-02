 pipeline
 {
    agent
    {
      label 'NODEJS'
     }
    stages {

       stage('prepare artifact')
       {
            steps
           {
              sh '''

                 zip -r payment.zip *

              '''
           }
       }
           stage('upload artifacts to nexus')
           {
              steps
              {
                 sh '''
                    curl -f -v -u admin:admin --upload-file payment.zip http://172.31.20.130:8081/repository/payment/payment.zip
                 '''

              }
           }


    }
 }
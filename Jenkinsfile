pipeline {
    agent any

    // environment {
    //     TOKEN     = credentials('clo')
    //
    // }

   stages() {
     stage('Test1' ) {
       steps {
         script {
           sh """
           echo HELLO
           pwd
           ls -li
           """


         }
        }
      }
   }
   post {
       success {

           archiveArtifacts allowEmptyArchive: true, artifacts: '${WORKSPACE}/simple-back-front/front/*.zip', fingerprint: true

       }
     }

 }

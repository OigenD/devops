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
           ansiblePlaybook extras: "-vv -u root --extra-vars \" inventory_dir=\"${WORKSPACE}/ansible/inventories/dev/\"\" ",
                         installation: 'ansible29',
                         inventory: "ansible/inventories/dev/inventory",
                         playbook: "ansible/test.yaml"

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

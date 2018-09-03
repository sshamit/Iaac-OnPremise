#!groovy

node {

    try {

       stage('Checkout'){

          checkout scm
       }


       stage('Build Docker'){
            echo 'Starting iso images process by packer'
            //sh 'packer.exe build ubuntu1604.json'
            echo 'Completed iso images process by packer'
       }

       stage('Deploy'){

         echo 'Started vagrant up'
         //sh 'vagrant up'
         echo 'Completed vagrant up'
         mail body: 'Vagrant up successful',
                     from: 'kushwaha_a@hcl.com',
                     replyTo: 'kushwaha_a@hcl.com',
                     subject: 'Vagrant up successful',
                     to: 'kushwaha_a@hcl.com'
       }



    }
    catch (err) {

        currentBuild.result = "FAILURE"

            mail body: "Vagrant up failed is here: ${env.BUILD_URL}" ,
                     from: 'kushwaha_a@hcl.com',
                     replyTo: 'kushwaha_a@hcl.com',
                     subject: 'Vagrant up successful',
                     to: 'kushwaha_a@hcl.com'

        throw err
    }

}

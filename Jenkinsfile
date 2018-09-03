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
       }



    }
    catch (err) {

        echo 'Your build failed due to some execption'

        throw err
    }

}

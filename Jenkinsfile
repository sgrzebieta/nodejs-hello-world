node('nodejs') {

    currentBuild.result = "SUCCESS"

    try {

       stage('Build'){

         env.NODE_ENV = "dev"

         print "Environment will be : ${env.NODE_ENV}"

         sh 'node -v'
         sh 'npm prune'
         sh 'npm install'

       }

       stage('Cleanup'){

         echo 'prune and cleanup'
         sh 'npm prune'
         sh 'rm node_modules -rf'
       }

    }
    catch (err) {

        currentBuild.result = "FAILURE"

        throw err
    }

}

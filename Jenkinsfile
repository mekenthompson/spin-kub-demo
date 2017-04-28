stage 'Checkout'
node {
   git 'https://github.com/mekenthompson/spin-kub-demo.git' // Checks out example votiung app repository
   stage 'Docker Builds'
   docker.withRegistry('', 'private-login') {
        parallel(
            "Build Vote App":{def myEnv = docker.build('f75c2xymvqv54.azurecr.io/azure-devops/spin-kub-demo:latest').push('latest')}
            )
    }
    stage 'Smoke Test'
    sh 'echo Smokeeeyyyyy'
}
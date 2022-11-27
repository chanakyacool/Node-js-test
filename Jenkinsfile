pipeline {
  agent any

  tools { nodejs "Nodejs-plugin" }

  stages{
      stage("Cloning git repo") {
        steps{
            git(
              url: 'git@github.com:chanakyacool/Node-js-test.git',
              credentialsId: '0b42ceee-8e1d-45ca-8099-0f324a42205e',
              branch: 'main'
              )
        }
      }
      stage('Buld dependencies'){
        steps{
            sh 'npm install'
        }
      }
      stage('Test'){
        steps{
            sh 'npm run test'
        }
      }
      stage('SLAnalyse'){
        steps{
          sh 'curl https://cdn.shiftleft.io/download/sl > ${env.WORKSPACE}/sl && chmod a+rx ${env.WORKSPACE}/sl'
          sh '${env.WORKSPACE}/sl auth $sl-org --token $sl-token'
          sh '${env.WORKSPACE}/sl analyze --app NodeJsTest --js --cpg ${env.WORKSPACE}/Node-js-test'
        }
      }
    }
}

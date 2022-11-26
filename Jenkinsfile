pipeline {
  agent any

  tools { nodejs "Nodejs-plugin" }

  stages{
      stage("Cloning git repo") {
        steps{
            git(
              url: 'git@github.com:chanakyacool/Node-js-test.git'
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
    }
}

pipeline {
  agent any

  tools { nodejs "Nodejs-plugin" }

  stages{
      stage("Cloning git repo") {
        steps{
            git 'https://github.com/chanakyacool/Node-js-test.git'
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

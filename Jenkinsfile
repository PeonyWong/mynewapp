pipeline {
   agent any
      environment {
         PATH='/usr/local/bin:/usr/bin:/bin'
      }
   stages {
      
      stage('NPM Setup') {
      steps {
         sh 'npm install'
      }
   }
      
   stage('Build') {
   steps {
      sh 'npm run build'
     } 
  }

   stage('install Capacitor') {
      steps {
       sh 'npm install --save @capacitor/core @capacitor/cli'
    }
   }

   stage('Add and copy iOS ') {
     steps {
        sh 'npx cap add ios'
        sh 'npx cap sync'
        sh 'npx cap copy'
     }
  }

 }
}

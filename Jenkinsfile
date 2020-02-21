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

   stage('Web Build') {
      steps {
        sh 'ionic serve'
    }
  }

   stage('install Capacitor') {
      steps {
       sh 'npm install --save @capacitor/core @capacitor/cli'
       sh 'npx cap init'
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

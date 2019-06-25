node {
    stage('Code Checkout') { // for display purposes
     echo 'Checout Code and clone it inside jenkins workspace.'
     git 'https://github.com/itrainavengers/maven_apps.git'
   }
   stage('Build Test & Package') {
      echo 'Build the package'
      sh 'mvn clean compile'
   }
   stage('Artifacts') {
       echo 'package the project artifacts..'
       sh 'mvn package'
   
   }
   stage('Deploy to Dev'){
       echo 'Deploy to Dev environment'
   }
   stage('Deploy to Test'){
       echo 'Deploy to Test environment'
   }
      stage('Test Automation'){
       echo 'Deploy to Dev environment'
   }
   
}

node {
    stage('Code Checkout') { // for display purposes
     echo 'Checout Code and clone it inside jenkins workspace.'
     git 'https://github.com/thadiwada/maven_apps.git'
   }
   stage('Build code') {
      echo 'Build the package'
      withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
       sh 'mvn clean compile'
     }
   }
   stage('SonarScan') {
      //withSonarQubeEnv('SonarQube') {
         //withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
             //sh 'mvn clean package sonar:sonar' 
             
          //   sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar' +
           //  ' -Dsonar.host.url=https://sonarcloud.io ' +
            // ' -Dsonar.organization=itrainavengers ' +
            // ' -Dsonar.login=c9515e84f9117ab6e598d26c34877938f72481a6 '   
         //}
       withSonarQubeEnv('SonarQube') {
           //sh 'mvn clean package org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar'
           sh 'mvn clean package sonar:sonar'
           
      }
   }
    
    
   stage('Artifacts') {
       echo 'package the project artifacts..'
       withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
       sh 'mvn package'
     }
   
   }
   stage('Deploy to Dev'){
       echo 'Deploy to Dev environment'
   }
   stage('Deploy to Test'){
       echo 'Deploy to Test environment'
   }
   stage('Deploy to Prod'){
       echo 'Deploy to Prod environment'
   }
      
   
}

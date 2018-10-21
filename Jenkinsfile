#!/usr/bin/env groovy

pipeline {

 agent any
 
 environment {
    MAJOR_VERSION = 1
}

 stages {

 stage('Unit Test') {
                  steps {
        sh 'ant -f test.xml -v'
        junit 'reports/result.xml'
                }
         
}  
  
 stage('Build') {
                  steps {
        sh 'ant -f build.xml -v'
                }
         
        }
  
  stage('Deploy') {
                  steps {
                   sh "cp dist/rectangle_${env.MAJOR_VERSION}.jar /var/www/html/rectangles/all/"
     
                }
         
}
  
  stage('Running on CentOS') {
   steps {
    sh "wget http://const19732.mylabserver.com/rectangles/all/rectangle_${env.MAJOR_VERSION}.jar"
    sh "java -jar rectangle_${env.MAJOR_VERSION}.jar 12 13"
    
   }
   
   
  }
  
  
  stage('Running on Debian') {
   agent {
   docker 'openjdk:8u121jre'
   }
   steps {
    sh "wget http://const19732.mylabserver.com/rectangles/all/rectangle_${env.MAJOR_VERSION}.jar"
    sh "java -jar rectangle_${env.MAJOR_VERSION}.jar 14 15"
    
   }
   
   
}
  
  
}

 post { 
  always {
         archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
         }
      }
}

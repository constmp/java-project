#!/usr/bin/env groovy

pipeline {

 agent any

 stages {

 stage('Build') {
                  steps {
        sh 'ant -f build.xml -v'
                }
         
        }
  
  stage('Test') {
                  steps {
        sh 'ant -f build.xml -v'
        junit 'reports/result.xml'
                }
         
}
  
}

 post { 
  always {
         archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
         }
      }
}
                                                                                                                                                                                                       
                                                                                                                                                                                                            
                                              

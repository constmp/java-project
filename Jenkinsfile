#!/usr/bin/env groovy

pipeline {

 agent any
 
 environment {
    MAJOR_VERSION = 1
}

 stages {

 stage('Build') {
                  steps {
        sh 'ant -f build.xml -v'
                }
         
        }
  
  stage('Test') {
                  steps {
        sh 'ant -f test.xml -v'
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
                                                                                                                                                                                                       
                                                                                                                                                                                                            
                                              

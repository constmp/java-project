pipeline {

agent any
 stages {
 stage('BUILD') {
      steps {
            sh 'ant -f build.xml -v'
            }
                 }
        }
 
 post {
  always {
         archive 'dist/*.jar'       
         }
 
       }
 
 
}
~                                                                                                                                                                                                            
~                                                                                                                                                                                                            
~                                               

# curl-test
This pipeline script will check speed of git repo
---------------------------------------------------------------------------------------
pipeline {
    agent none
      stages {
            stage('DTL Check'){
                agent {
                node {
                    label ("PROD-LIN1")
                }
            }
                steps {
                     sh 'wget https://github.com/narendras2008/helloworld-java-maven'
                                     }
           }
            stage('check'){
                agent {
                node {
                    label ("DTL-LIN1")
                     }
                    }
                steps {
                    sh 'wget https://github.com/narendras2008/cucumberbasic' 
                                          }
            }   
        }        
         }   
        
